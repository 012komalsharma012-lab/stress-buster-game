const canvas = document.getElementById("bossCanvas");
const ctx = canvas.getContext("2d");
let score = 0;
let angry = false;

function drawFace() {
  ctx.clearRect(0, 0, 300, 300);

  ctx.fillStyle = angry ? "red" : "#f5cba7";
  ctx.beginPath();
  ctx.arc(150, 150, 140, 0, Math.PI * 2);
  ctx.fill();
}

function punchBoss() {
  angry = true;
  score++;
  document.getElementById("score").innerText = score;
  drawFace();

  setTimeout(() => {
    angry = false;
    drawFace();
  }, 500);
}

function clearFace() {
  drawFace();
}

drawFace();
