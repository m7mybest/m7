/* JACKPOT */

const startTime=new Date("2026-03-01").getTime();

function updateJackpots(){

let seconds=(Date.now()-startTime)/1000;

let mega=15000+seconds*(700/86400);
let major=5000+seconds*(450/86400);
let minor=1500+seconds*(180/86400);

document.getElementById("mega").innerText="RM "+mega.toLocaleString("en-MY",{minimumFractionDigits:2,maximumFractionDigits:2});
document.getElementById("major").innerText="RM "+major.toLocaleString("en-MY",{minimumFractionDigits:2,maximumFractionDigits:2});
document.getElementById("minor").innerText="RM "+minor.toLocaleString("en-MY",{minimumFractionDigits:2,maximumFractionDigits:2});

/* Jackpot 闪光效果 */

document.getElementById("mega").classList.add("jackpot-flash");
document.getElementById("major").classList.add("jackpot-flash");
document.getElementById("minor").classList.add("jackpot-flash");

setTimeout(()=>{
document.getElementById("mega").classList.remove("jackpot-flash");
document.getElementById("major").classList.remove("jackpot-flash");
document.getElementById("minor").classList.remove("jackpot-flash");
},500);

}

updateJackpots();
setInterval(updateJackpots,200);

/* BTC 随机掉落 */

for(let i=0;i<40;i++){

let coin=document.createElement("img");

coin.src="btc.png";

/* 随机层次 */
let layer=Math.random();

if(layer<0.33){
coin.className="coin far";
}
else if(layer<0.66){
coin.className="coin mid";
}
else{
coin.className="coin near";
}

coin.style.left=Math.random()*100+"%";

coin.style.animationDuration=(Math.random()*10+10)+"s";

coin.style.animationDelay=-(Math.random()*20)+"s";

coin.style.width=(Math.random()*25+20)+"px";

document.getElementById("coins").appendChild(coin);

}

function toggleLang(event){

event.stopPropagation();

let menu=document.querySelector(".lang-menu");

if(menu.style.display==="block"){
menu.style.display="none";
}else{
menu.style.display="block";
}

}

function setLang(lang){

document.querySelectorAll(".lang").forEach(el=>{
el.style.display="none";
});

document.querySelectorAll("." + lang).forEach(el=>{
el.style.display="block";
});

localStorage.setItem("lang",lang);

if(lang==="bm"){
document.getElementById("currentLang").innerText="BM";
}

if(lang==="en"){
document.getElementById("currentLang").innerText="EN";
}

if(lang==="cn"){
document.getElementById("currentLang").innerText="中文";
}

/* 选择语言后关闭菜单 */
document.querySelector(".lang-menu").style.display="none";

}

function detectLang(){

let saved=localStorage.getItem("lang");

if(saved){
setLang(saved);
return;
}

let lang=navigator.language;

if(lang.includes("zh")){
setLang("cn");
}
else if(lang.includes("ms")){
setLang("bm");
}
else{
setLang("en");
}

}

detectLang();

  /* 点击页面关闭语言菜单 */

document.addEventListener("click",function(e){

let menu=document.querySelector(".lang-menu");
let button=document.querySelector(".lang-current");

if(menu && button){
if(!menu.contains(e.target) && !button.contains(e.target)){
menu.style.display="none";
}
}

});

/* 禁止右键 */
document.addEventListener("contextmenu",function(e){
e.preventDefault();
});

/* 禁止 F12 */
document.onkeydown=function(e){

if(e.keyCode==123){
return false;
}

if(e.ctrlKey && e.shiftKey && e.keyCode==73){
return false;
}

if(e.ctrlKey && e.keyCode==85){
return false;
}

};


/* 禁止复制 */
document.addEventListener("copy",function(e){
e.preventDefault();
});

/* 禁止选中文字 */
document.addEventListener("selectstart",function(e){
e.preventDefault();
});



/* 禁止拖拽图片 */
document.addEventListener("dragstart",function(e){
e.preventDefault();
});

let devtoolsOpen = false;

setInterval(function(){

const widthDiff = window.outerWidth - window.innerWidth;
const heightDiff = window.outerHeight - window.innerHeight;

if(widthDiff > 160 || heightDiff > 160){
devtoolsOpen = true;
}

if(devtoolsOpen){
document.body.innerHTML="";
}

},500);
