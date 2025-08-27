<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<title>⚠️ 系統錯誤</title>
<style>
body {
  margin:0;
  overflow:hidden;
  font-family: monospace;
  background:black;
  color:white;
}
.random-text{
  position:absolute;
  font-size:32px;
  font-weight:bold;
  animation: spin 1s infinite linear, flash 0.2s infinite alternate;
}
@keyframes spin{
  from{transform:rotate(0deg);}
  to{transform:rotate(360deg);}
}
@keyframes flash{
  from{opacity:0.3;}
  to{opacity:1;}
}
.warning{
  position:fixed;
  top:30%;
  left:50%;
  transform:translate(-50%,-50%);
  background:red;
  color:white;
  padding:20px;
  font-size:28px;
  border:5px solid yellow;
  text-align:center;
  z-index:9999;
  animation:blink 0.3s infinite;
}
@keyframes blink{
  0%{background:red;}
  50%{background:black;}
  100%{background:red;}
}
</style>
</head>
<body>
<div class="warning">⚠️ 你的電腦已被魔幻影鎖定<br>請立即訂閱否則資料將被刪除 ⚠️</div>

<script>
setInterval(()=>{
  let span = document.createElement("span");
  span.className="random-text";
  span.innerText = randomChar();
  span.style.left = Math.random()*window.innerWidth+"px";
  span.style.top = Math.random()*window.innerHeight+"px";
  span.style.color = randomColor();
  span.style.fontSize = (20+Math.random()*50)+"px";
  document.body.appendChild(span);
  setTimeout(()=>{span.remove();},1000);
},5); // 刷字速度 超快

// 閃爍背景
setInterval(()=>{
  document.body.style.background = randomColor();
},100);

function randomChar(){
  const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789🤡🤓👾💀🔥⚡🚨🦠";
  return chars.charAt(Math.floor(Math.random()*chars.length));
}
function randomColor(){
  const r = Math.floor(Math.random()*255);
  const g = Math.floor(Math.random()*255);
  const b = Math.floor(Math.random()*255);
  return `rgb(${r},${g},${b})`;
}
</script>
</body>
</html>
