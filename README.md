<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>I Love You Rub ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

body{
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:radial-gradient(circle at top,#1a0014,#000);
  overflow:hidden;
  font-family:'Segoe UI',sans-serif;
}

#container{
  text-align:center;
}

#text{
  font-size:3.2rem;
  letter-spacing:5px;
  color:#ff4d6d;
  text-align:center;
}

/* Letter animation */
#text span{
  opacity:0;
  display:inline-block;
  animation:show 0.6s forwards;
}

@keyframes show{
  from{
    opacity:0;
    transform:translateY(30px);
    filter:blur(6px);
  }
  to{
    opacity:1;
    transform:translateY(0);
    filter:blur(0);
    text-shadow:
      0 0 10px #ff4d6d,
      0 0 25px #ff6b81,
      0 0 40px #ff9aa2;
  }
}

/* Tap message */
#tap{
  margin-top:20px;
  font-size:1rem;
  color:#ffd6e0;
  opacity:0.9;
  animation:blink 1.5s infinite;
}

@keyframes blink{
  0%{opacity:0.3;}
  50%{opacity:1;}
  100%{opacity:0.3;}
}

/* Mobile */
@media(max-width:600px){
  #text{
    font-size:2rem;
    letter-spacing:3px;
  }
}
</style>
</head>

<body>

<div id="container">
  <div id="text"></div>
  <div id="tap">Tap to feel the love 💖</div>
</div>

<audio id="music" loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_7c8c8c7a2a.mp3?filename=romantic-ambient-112191.mp3" type="audio/mpeg">
</audio>

<script>
const message = "I LOVE YOU RUB ❤️";
const textDiv = document.getElementById("text");
const tapText = document.getElementById("tap");
const music = document.getElementById("music");

const delayPerLetter = 150;
const totalDuration = message.length * delayPerLetter + 2000;

function animateText(){
  textDiv.innerHTML = "";
  message.split("").forEach((char,index)=>{
    const span = document.createElement("span");
    span.innerHTML = char === " " ? "&nbsp;" : char;
    span.style.animationDelay = (index * delayPerLetter) + "ms";
    textDiv.appendChild(span);
  });
}

// First run
animateText();

// Loop
setInterval(animateText, totalDuration);

// Start music on first click
document.body.addEventListener("click", ()=>{
  music.play();
  tapText.style.display = "none";
},{ once:true });
</script>

</body>
</html># I-love-you-Bby
