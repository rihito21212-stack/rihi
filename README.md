let score = 0;
let time = 10;
let timer = null;
let isPlaying = false;

const scoreEl = document.getElementById("score");
const timeEl = document.getElementById("time");
const clickBtn = document.getElementById("clickBtn");
const startBtn = document.getElementById("startBtn");

clickBtn.addEventListener("click", () => {
  if (!isPlaying) return;
  score++;
  scoreEl.textContent = score;
});

startBtn.addEventListener("click", () => {
  if (isPlaying) return;

  score = 0;
  time = 10;
  scoreEl.textContent = score;
  timeEl.textContent = time;
  isPlaying = true;

  timer = setInterval(() => {
    time--;
    timeEl.textContent = time;

    if (time <= 0) {
      clearInterval(timer);
      isPlaying = false;
      alert("ゲーム終了！スコア: " + score);
    }
  }, 1000);
});
