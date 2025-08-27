<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>魔幻影Sksnki介紹</title>
<style>
body {
  margin: 0;
  font-family: "Microsoft JhengHei", sans-serif;
  text-align: center;
  background: #000;
  color: #0ff;
  overflow: hidden;
}

/* 閃爍警告 */
#virusWarning {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: red;
  color: yellow;
  font-size: 2em;
  font-weight: bold;
  padding: 10px;
  z-index: 10000;
  text-shadow: 0 0 10px #fff, 0 0 20px #f00;
  animation: blink 0.3s infinite alternate;
  display: none;
}

@keyframes blink {
  0% { background: red; color: yellow; }
  100% { background: yellow; color: red; }
}

/* 自訂彈窗 */
#customModal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.85);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
}

#modalBox {
  background: #111;
  padding: 30px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 0 20px #0ff, 0 0 40px #00f;
  animation: glow 1.5s infinite alternate;
}

@keyframes glow {
  from { box-shadow: 0 0 20px #0ff, 0 0 40px #00f; }
  to   { box-shadow: 0 0 40px #ff0, 0 0 80px #f0f; }
}

#modalBox h2 {
  color: #0ff;
  margin-bottom: 20px;
  text-shadow: 0 0 10px #0ff, 0 0 20px #00f;
}

/* 彈窗按鈕 */
.modal-btn {
  padding: 12px 25px;
  margin: 10px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  font-size: 1.1em;
  transition: 0.3s;
  color: #fff;
}
#yesBtn { background: linear-gradient(45deg, #00ff99, #00cc66); box-shadow:0 0 15px #00ff99,0 0 30px #00cc66;}
#yesBtn:hover { transform: scale(1.1); }
#noBtn { background: linear-gradient(45deg, #ff0066, #cc0033); box-shadow:0 0 15px #ff0066,0 0 30px #cc0033;}
#noBtn:hover { transform: scale(1.1); }

/* 簡介內容 */
#mainContent img {
  width: 90%;
  max-width: 600px;
  border-radius: 10px;
  margin-top: 20px;
  box-shadow: 0 0 20px #0ff, 0 0 40px #0055ff;
}

#mainContent p {
  font-size: 1.2em;
  line-height: 1.6;
  color: #fff;
  max-width: 600px;
  margin: 15px auto;
}
</style>
</head>
<body>

<!-- 閃爍警告 -->
<div id="virusWarning">⚠️ 你中病毒了 ⚠️</div>

<!-- 彈窗 -->
<div id="customModal">
  <div id="modalBox">
    <h2>你有訂閱魔幻影嗎？</h2>
    <button class="modal-btn" id="yesBtn">已訂閱</button>
    <button class="modal-btn" id="noBtn">未訂閱</button>
  </div>
</div>

<!-- 正常介紹 -->
<div id="mainContent" style="display:none;">
  <h1>魔幻影 Sksnki介紹</h1>
  <p>嗨嗨，我是魔幻影Sksnki，是一位台灣的 YouTube。<br>
     主要拍 ROBLOX，有時會舉辦抽獎，記得訂閱我！</p>
  <img src="IMG_6226CCFE5FA0-1.jpeg" alt="魔幻影Sksnki 照片">
</div>

<script>
const modal = document.getElementById("customModal");
const mainContent = document.getElementById("mainContent");
const virusWarning = document.getElementById("virusWarning");
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");

yesBtn.onclick = () => {
  modal.style.display = "none";
  mainContent.style.display = "block";
};

noBtn.onclick = () => {
  modal.style.display = "none";
  virusWarning.style.display = "block";
  document.body.style.background = "#000";
  // 亂碼生成
  setInterval(() => {
    const span = document.createElement("span");
    const chars = "abcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()🤓👍💀☠️";
    span.textContent = chars.charAt(Math.floor(Math.random()*chars.length));
    span.style.color = `hsl(${Math.random()*360},100%,50%)`;
    span.style.position = "absolute";
    span.style.left = Math.random()*window.innerWidth + "px";
    span.style.top = Math.random()*window.innerHeight + "px";
    span.style.fontSize = `${Math.random()*25+15}px`;
    span.style.fontWeight = "bold";
    document.body.appendChild(span);
    
    // 飄動效果
    let top = parseFloat(span.style.top);
    const move = setInterval(() => {
      top += 1 + Math.random()*5;
      span.style.top = top + "px";
      if(top>window.innerHeight) clearInterval(move);
    }, 30);
  }, 30);
};
</script>

</body>
</html>
