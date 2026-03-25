<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ranjit Kumar Sahoo | Portfolio</title>

<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
* { margin:0; padding:0; box-sizing:border-box; }

body {
    font-family: 'Poppins', sans-serif;
    color:white;
    background: linear-gradient(-45deg,#0f2027,#203a43,#2c5364,#000);
    background-size:400% 400%;
    animation: gradient 10s ease infinite;
}

@keyframes gradient {
    0% {background-position:0%}
    50% {background-position:100%}
    100% {background-position:0%}
}

.container {
    width:90%;
    margin:auto;
    padding:30px 0;
}

h1 {
    font-family:'Orbitron';
    font-size:3rem;
    color:#00ffff;
}

.glow {
    color:#00ffff;
    text-shadow:0 0 10px #00ffff;
}

.section {
    margin:40px 0;
    padding:20px;
    border-radius:15px;
    background:rgba(255,255,255,0.08);
    backdrop-filter:blur(12px);
}

button {
    padding:10px 20px;
    border:none;
    border-radius:8px;
    background:#00ffff;
    cursor:pointer;
}

/* typing */
.typing {
    border-right:2px solid #00ffff;
    white-space:nowrap;
    overflow:hidden;
    width:0;
    animation: typing 3s steps(30,end) forwards;
}
@keyframes typing {
    to { width:100% }
}

/* game */
.game {
    display:grid;
    grid-template-columns:repeat(3,100px);
    gap:10px;
    justify-content:center;
}
.cell {
    height:100px;
    display:flex;
    justify-content:center;
    align-items:center;
    background:#111;
    font-size:2rem;
    cursor:pointer;
}

/* chatbot */
.chatbox {
    height:200px;
    overflow:auto;
    background:#111;
    padding:10px;
}
input {
    width:80%;
    padding:10px;
}
</style>
</head>

<body>

<div class="container">

<!-- HERO -->
<h1>Hi 👋 I'm <span class="glow">Ranjit Kumar Sahoo</span></h1>
<h2 class="typing">AI/ML Engineer | Full Stack Developer</h2>

<!-- ABOUT -->
<div class="section">
<h2>🚀 About Me</h2>
<p>CGPA 9.91 | Generative AI | Cloud | Hackathon Winner</p>
<a href="#"><button>📄 Download Resume</button></a>
</div>

<!-- SKILLS -->
<div class="section">
<h2>⚡ Tech Stack</h2>
<p>Python | Java | C++ | React | Node | ML | AWS</p>
</div>

<!-- GITHUB -->
<div class="section">
<h2>📊 GitHub Stats</h2>
<img src="https://github-readme-stats.vercel.app/api?username=sahooranjitlipun&show_icons=true&theme=tokyonight" width="100%">
</div>

<!-- MUSIC -->
<div class="section">
<h2>🎵 Music</h2>
<iframe style="border-radius:12px" 
src="https://open.spotify.com/embed/playlist/37i9dQZF1DXcBWIGoYBM5M" 
width="100%" height="150"></iframe>
</div>

<!-- GAME -->
<div class="section">
<h2>🎮 Mini Game</h2>
<div class="game" id="game"></div>
</div>

<!-- CHATBOT -->
<div class="section">
<h2>🤖 Ask Me Anything</h2>
<div class="chatbox" id="chat"></div>
<input id="msg" placeholder="Ask about Ranjit...">
<button onclick="send()">Send</button>
</div>

<!-- CONTACT -->
<div class="section">
<h2>📬 Contact Me</h2>
<p>Email: yourmail@gmail.com</p>
<p><a href="https://www.linkedin.com/">LinkedIn</a></p>
</div>

</div>

<script>

/* GAME */
let board=["","","","","","","","",""];
let current="X";
const game=document.getElementById("game");

board.forEach((_,i)=>{
 let cell=document.createElement("div");
 cell.classList.add("cell");
 cell.onclick=()=>move(i,cell);
 game.appendChild(cell);
});

function move(i,cell){
 if(board[i]==""){
  board[i]=current;
  cell.innerText=current;
  current=current=="X"?"O":"X";
 }
}

/* CHATBOT */
function send(){
 let input=document.getElementById("msg");
 let chat=document.getElementById("chat");

 let user=input.value;
 chat.innerHTML+="<p>👤 "+user+"</p>";

 let reply="I'm Ranjit's AI assistant 🤖. He is strong in AI, ML, and Full Stack.";

 if(user.toLowerCase().includes("skills")){
  reply="Python, React, ML, Cloud ☁️";
 }

 chat.innerHTML+="<p>🤖 "+reply+"</p>";
 input.value="";
}

</script>

</body>
</html>
