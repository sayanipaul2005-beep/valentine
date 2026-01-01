<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Forever Valentine 💖</title>
<style>
body{
  margin:0;
  height:100vh;
  background:linear-gradient(#ffd1dc,#fff);
  display:flex;
  justify-content:center;
  align-items:center;
  font-family:'Comic Sans MS', cursive;
  overflow:hidden;
}

.scene{
  width:100%;
  max-width:900px;
  height:380px;
  position:relative;
}

.title{
  text-align:center;
  font-size:30px;
  color:#ff3366;
}

.names{
  text-align:center;
  font-size:22px;
  color:#ff5c8a;
}

.girl,.boy{
  position:absolute;
  bottom:70px;
}

.girl{
  left:-120px;
  animation:run 5s forwards;
}

.boy{
  right:120px;
}

.head{
  width:40px;
  height:40px;
  background:#ffb6c1;
  border-radius:50%;
  margin:auto;
}

.body{
  width:10px;
  height:60px;
  background:#333;
  margin:auto;
}

.bouquet{
  width:26px;
  height:26px;
  background:red;
  border-radius:50%;
  position:absolute;
  right:-18px;
  top:50px;
}

.question{
  position:absolute;
  top:-20px;
  width:100%;
  text-align:center;
  font-size:26px;
  color:#ff3366;
  opacity:0;
  animation:show 2s forwards;
  animation-delay:5.5s;
}

.buttons{
  position:absolute;
  top:60px;
  width:100%;
  text-align:center;
  opacity:0;
  animation:show 2s forwards;
  animation-delay:6.5s;
}

button{
  padding:12px 26px;
  font-size:18px;
  border:none;
  border-radius:25px;
  cursor:pointer;
  margin:10px;
}

#yes{
  background:#ff4d6d;
  color:white;
}

#no{
  background:#ccc;
}

.message{
  position:absolute;
  top:120px;
  width:100%;
  text-align:center;
  font-size:28px;
  color:#ff3366;
  display:none;
}

.countdown{
  position:absolute;
  bottom:10px;
  width:100%;
  text-align:center;
  font-size:18px;
  color:#ff5c8a;
}

.heart{
  position:absolute;
  width:20px;
  height:20px;
  background:red;
  transform:rotate(45deg);
  animation:float 6s infinite;
}

.heart::before,.heart::after{
  content:"";
  width:20px;
  height:20px;
  background:red;
  border-radius:50%;
  position:absolute;
}

.heart::before{top:-10px;}
.heart::after{left:-10px;}

.confetti{
  position:absolute;
  width:8px;
  height:8px;
  background:#ff4d6d;
  animation:confetti 3s linear forwards;
}

@keyframes run{
  0%{left:-120px;}
  70%{left:55%;}
  100%{left:55%;transform:translateY(20px);}
}

@keyframes show{to{opacity:1;}}

@keyframes float{
  0%{bottom:0;opacity:1;}
  100%{bottom:380px;opacity:0;}
}

@keyframes confetti{
  from{top:0;opacity:1;}
  to{top:380px;opacity:0;}
}
</style>
</head>

<body>

<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<div class="scene">

<div class="title">💖 A Special Moment 💖</div>
<div class="names">Sayani & Sanubhav</div>

<div class="question">
Will you be my Valentine for the rest of the year? 🌹
</div>

<div class="buttons">
<button id="yes">YES 💘</button>
<button id="no">NO 🙈</button>
</div>

<div class="message" id="loveMsg">
YAYYYYY 😭💖<br>
Forever starts now 💍💞
</div>

<div class="girl">
  <div class="head"></div>
  <div class="body"></div>
  <div class="bouquet"></div>
</div>

<div class="boy">
  <div class="head"></div>
  <div class="body"></div>
</div>

<div class="countdown" id="countdown"></div>

<!-- hearts -->
<div class="heart" style="left:10%;animation-delay:0s"></div>
<div class="heart" style="left:30%;animation-delay:2s"></div>
<div class="heart" style="left:50%;animation-delay:4s"></div>
<div class="heart" style="left:70%;animation-delay:1s"></div>
<div class="heart" style="left:90%;animation-delay:3s"></div>

</div>

<script>
const yes=document.getElementById("yes");
const no=document.getElementById("no");
const msg=document.getElementById("loveMsg");

yes.onclick=()=>{
  msg.style.display="block";

  for(let i=0;i<80;i++){
    let c=document.createElement("div");
    c.className="confetti";
    c.style.left=Math.random()*100+"%";
    c.style.background=["#ff4d6d","#ffd166","#cdb4db"][Math.floor(Math.random()*3)];
    document.body.appendChild(c);
    setTimeout(()=>c.remove(),3000);
  }
}

no.onmouseover=()=>{
  no.style.position="absolute";
  no.style.left=Math.random()*80+"%";
  no.style.top=Math.random()*80+"%";
}

// Countdown
const target=new Date("Feb 14, 2026").getTime();
setInterval(()=>{
  let now=new Date().getTime();
  let d=target-now;
  if(d>0){
    let days=Math.floor(d/(1000*60*60*24));
    document.getElementById("countdown").innerHTML=
      "⏳ Valentine’s Day in "+days+" days";
  }
},1000);
</script>

</body>
</html>
