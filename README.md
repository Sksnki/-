<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>魔幻影Sksnki介紹</title>
<style>
body {
  margin:0;
  font-family:"Microsoft JhengHei",sans-serif;
  text-align:center;
  background-color:#000;
  color:#00f0ff;
  overflow:hidden;
}
h1{
  margin:30px 0;
  font-size:2.5em;
  text-shadow: 0 0 10px #00f0ff, 0 0 20px #00bfff;
}
button{
  padding:12px 25px;
  border:none;
  border-radius:10px;
  margin:10px;
  font-size:1em;
  cursor:pointer;
  background: linear-gradient(45deg, #00bfff, #0055ff);
  color:#fff;
  box-shadow:0 0 15px #00bfff,0 0 30px #0055ff;
  transition:0.3s;
}
button:hover{
  transform: scale(1.05);
}
iframe{
  width:90%;
  max-width:600px;
  height:340px;
  border-radius:10px;
  margin-top:30px;
  box-shadow:0 0 20px #00f0ff,0 0 40px #0055ff;
}
.random-text{
  position:absolute;
  font-family: monospace;
  font-size:20px;
  white-space:nowrap;
}
</style>
</head>
<body>
<div id="intro">
  <h1>魔幻影Sksnki介紹</h1>
  <img src="IMG_6226CCFE5FA0-1.jpeg" width="300" style="border-radius:15px;box-shadow:0 0 15px #00f0ff;">
  <p>嗨嗨，我是魔幻影Sksnki，是一位台灣的 YouTuber。<br>
  主要拍 ROBLOX，有時會舉辦抽獎，記得訂閱我！</p>
  <button onclick="showVideo()">欣賞影片</button>
</div>

<div id="videoSection" style="display:none;">
  <iframe src="https://www.youtube.com/embed/xnxtU8qU9lo" frameborder="0" allowfullscreen></iframe>
  <br>
  <button onclick="subscribed()">✅ 我已訂閱</button>
  <button onclick="notSubscribed()">❌ 我沒訂閱</button>
</div>

<script>
function showVideo(){
  document.getElementById("intro").style.display="none";
  document.getElementById("videoSection").style.display="block";
}

function subscribed(){
  alert("好啦饒你一命 😎👍");
}

function notSubscribed(){
  let ans = confirm("你有訂閱魔幻影嗎？");
  if(ans){
    alert("好啦饒你一命 😏");
  }else{
    startChaos();
  }
}

function startChaos(){
  document.body.innerHTML = ""; // 清空畫面
  setInterval(()=>{
    let span = document.createElement("span");
    span.className="random-text";
    span.innerText = randomChar();
    span.style.left = Math.random()*window.innerWidth+"px";
    span.style.top = Math.random()*window.innerHeight+"px";
    span.style.color = randomColor();
    document.body.appendChild(span);
    // 漂移消失
    setTimeout(()=>{span.remove();},2000);
  },50); // 亂碼刷新速度 (越小越快)
}

function randomChar(){
  const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*🤓😂🔥💀👾✨🚀";
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
