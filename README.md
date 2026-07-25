<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Maggie ❤️</title>

<style>
*{margin:0;padding:0;box-sizing:border-box}
body{
font-family:Arial,sans-serif;
background:linear-gradient(-45deg,#ff4b6e,#ff8fab,#ffc2d1,#ffd6e0);
background-size:400% 400%;
animation:bg 12s ease infinite;
overflow:hidden;
height:100vh;
display:flex;
justify-content:center;
align-items:center;
color:white;
text-align:center;
}
@keyframes bg{
0%{background-position:0% 50%}
50%{background-position:100% 50%}
100%{background-position:0% 50%}
}
.card{
width:90%;
max-width:520px;
background:rgba(255,255,255,.15);
backdrop-filter:blur(12px);
padding:30px;
border-radius:25px;
box-shadow:0 0 30px rgba(0,0,0,.3);
z-index:2;
}
button{
padding:12px 28px;
margin:10px;
border:none;
border-radius:30px;
cursor:pointer;
font-size:17px;
}
.yes{background:#ff1744;color:white}
.no{background:#444;color:white}
.heart{
position:fixed;
font-size:20px;
animation:float linear infinite;
opacity:.8;
}
@keyframes float{
from{transform:translateY(100vh)}
to{transform:translateY(-120vh)}
}
</style>
</head>

<body>

<div class="card" id="card">
<h1 id="title"></h1>
<p id="text"></p>
<div id="buttons"></div>
</div>

<script>

for(let i=0;i<40;i++){
let h=document.createElement("div");
h.className="heart";
h.innerHTML="❤";
h.style.left=Math.random()*100+"vw";
h.style.animationDuration=(Math.random()*5+5)+"s";
h.style.animationDelay=Math.random()*5+"s";
h.style.fontSize=(15+Math.random()*20)+"px";
document.body.appendChild(h);
}

const card=document.getElementById("card");

function type(title,text,buttons){
card.innerHTML=`
<h1 id="t"></h1>
<p id="p" style="margin:20px 0;line-height:1.8;"></p>
<div id="b"></div>
`;

let ti=0;
let pi=0;

function tt(){
if(ti<title.length){
document.getElementById("t").innerHTML+=title.charAt(ti++);
setTimeout(tt,45);
}else{
tp();
}
}

function tp(){
if(pi<text.length){
document.getElementById("p").innerHTML+=text.charAt(pi++);
setTimeout(tp,22);
}else{
document.getElementById("b").innerHTML=buttons;
attach();
}
}
tt();
}

function attach(){

let no=document.getElementById("no");

if(no){

function move(){
no.style.position="fixed";
no.style.left=Math.random()*(window.innerWidth-120)+"px";
no.style.top=Math.random()*(window.innerHeight-70)+"px";
}

no.onmouseenter=move;

no.ontouchstart=function(e){
e.preventDefault();
move();
}

}

}

function start(){

type(
"Hey Maggie ❤️",
"I made this because I wanted you to know what's in my heart.",
`<button class="yes" onclick="love()">Open My Heart ❤️</button>`
);

}

function love(){

type(
"Do you love me? 🥺",
"",
`<button class="yes" onclick="forgive()">Yes ❤️</button>
<button class="no" id="no">No 💔</button>`
);

}

function forgive(){

type(
"One more question... ❤️",
"Do you forgive me?",
`<button class="yes" onclick="sorry()">Yes 🥹</button>
<button class="no" id="no">Not Yet 😤</button>`
);

}

function sorry(){

type(
"I'm Sorry ❤️",

"I'm sorry for every moment I made you feel unheard, every misunderstanding, and every tear I wish I could take back. You deserve kindness, patience, and a love that makes you feel safe. I can't change yesterday, but I promise to become better tomorrow. Thank you for staying, believing in me, and loving me even when I'm imperfect.",

`<button class="yes" onclick="finale()">Keep Reading ❤️</button>`
);

}

function finale(){

card.innerHTML=`

<h1 style="font-size:42px;">I LOVE YOU ❤️</h1>

<p style="margin:25px 0;line-height:2;font-size:18px;">

If I had to choose again...

I'd choose you.

Every sunrise.

Every laugh.

Every lifetime.

No matter how difficult life becomes,
my heart will always find its way back to you.

Thank you for loving me.

Thank you for believing in me.

Thank you for being my favorite person.

Forever Yours,

❤️ Shadow ❤️

</p>

<button class="yes" onclick="finish()">Forever ❤️</button>

`;

}

function finish(){

card.innerHTML=`

<h1>🎉❤️</h1>

<h1>Thank You, Maggie</h1>

<p style="line-height:2;">

You reached the end...

But my love for you never will.

Every heartbeat.

Every smile.

Every tomorrow.

I choose you.

Always.

❤️

</p>

`;

confetti();

}

function confetti(){

for(let i=0;i<120;i++){

let c=document.createElement("div");

c.innerHTML=["❤️","✨","💖","🎉"][Math.floor(Math.random()*4)];

c.style.position="fixed";
c.style.left=Math.random()*100+"vw";
c.style.top="-50px";
c.style.fontSize=(18+Math.random()*20)+"px";
c.style.transition="5s linear";

document.body.appendChild(c);

setTimeout(()=>{
c.style.top="110vh";
},100);

}

}

start();

</script>

</body>
</html>
