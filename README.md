let score = 0;
let best = 0;

const scoreEl = document.querySelector("h1");
const bestEl = document.querySelector("p");

function updateScore() {
  score++;
  scoreEl.textContent = score;
  if (score > best) {
    best = score;
    bestEl.textContent = "BEST: " + best;
  }
}

// Mobile aur desktop dono ke liye
document.body.addEventListener("click", updateScore);
document.body.addEventListener("touchstart", updateScore);
