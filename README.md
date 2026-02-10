<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>For Hipo 💝</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">

<style>
body{
margin:0;
font-family:Poppins;
text-align:center;
color:white;
overflow:hidden;
background:linear-gradient(-45deg,#ff6a88,#ff99ac,#ffc3a0,#ff6a88);
background-size:400% 400%;
animation:bg 10s ease infinite;
}

@keyframes bg{
0%{background-position:0% 50%}
50%{background-position:100% 50%}
100%{background-position:0% 50%}
}

.card{
background:rgba(255,255,255,0.15);
backdrop-filter:blur(12px);
border-radius:20px;
padding:30px;
max-width:650px;
margin:auto;
margin-top:12vh;
box-shadow:0 10px 30px rgba(0,0,0,0.25);
}

button{
padding:14px 26px;
border:none;
border-radius:30px;
font-size:18px;
cursor:pointer;
margin:10px;
background:white;
color:#ff4d6d;
transition:.3s;
}

button:hover{transform:scale(1.1)}

.section{display:none}
.show{display:block}

.musicBtn{
position:fixed;
top:15px;
right:15px;
font-size:14px;
padding:10px 16px;
}

/* gift box */
.gift{
font-size:90px;
cursor:pointer;
animation:bounce 1.2s infinite;
}

@keyframes bounce{
0%,100%{transform:translateY(0)}
50%{transform:translateY(-15px)}
}

.heart{
position:fixed;
top:-10px;
font-size:20px;
animation:fall linear forwards;
}

@keyframes fall{
to{transform:translateY(110vh)}
}
</style>
</head>

<body>

<button class="musicBtn" onclick="toggleMusic()">🎵 Music</button>

<audio id="bgMusic" loop>
<source src="music.mp3" type="audio/mpeg">
</audio>

<!-- Screen 1 -->
<div id="s1" class="section show">
<div class="card">
<h1>Hey Hipo ✨</h1>
<p>Mahi ne tumhare liye ek surprise banaya hai</p>
<div class="gift" onclick="next('s2')">🎁</div>
<p>Tap the gift</p>
</div>
</div>

<!-- Screen 2 typing -->
<div id="s2" class="section">
<div class="card">
<h2 id="typing"></h2>
<button onclick="next('s3')">Next ➜</button>
</div>
</div>

<!-- Screen 3 message -->
<div id="s3" class="section">
<div class="card">
<p>
Mujhe nahi pata ki tum mujhe q itne acche lagte ho  
par acche lagte ho… bahot acche lagte ho.  
Aage bhi lagte rahoge 🙂
<br><br>
Mujhe nahi pata main kya feel karti hu  
par jo bhi feeling hai — bahot acchi hai 💫  
Aur hope hai ye kabhi khatam na ho.
</p>
<button onclick="next('s4')">Final ➜</button>
</div>
</div>

<!-- Final -->
<div id="s4" class="section">
<div class="card">
<h1>Always Smile 😊</h1>
<h2>— Mahi</h2>
</div>
</div>

<script>
function next(id){
document.querySelectorAll('.section').forEach(s=>s.classList.remove('show'));
document.getElementById(id).classList.add('show');
}

/* typing effect */
const text = "Tum mere liye special ho 🌸";
let i=0;
function type(){
if(i<text.length){
document.getElementById("typing").innerHTML += text.charAt(i);
i++;
setTimeout(type,60);
}}
type();

/* music */
const music=document.getElementById("bgMusic");
let playing=false;
function toggleMusic(){
if(!playing){music.play();playing=true;}
else{music.pause();playing=false;}
}

/* hearts */
setInterval(()=>{
const h=document.createElement("div");
h.className="heart";
h.innerHTML="💖";
h.style.left=Math.random()*100+"vw";
h.style.animationDuration=(3+Math.random()*3)+"s";
document.body.appendChild(h);
setTimeout(()=>h.remove(),6000);
},400);
</script>

</body>
</html>
