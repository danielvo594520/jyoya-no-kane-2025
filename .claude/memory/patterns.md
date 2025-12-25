# patterns.md - 再利用パターン

プロジェクトで確立されたパターンや規約を記録します。

---

## P1: Canvas ゲームループパターン

```javascript
const canvas = document.getElementById('game');
const ctx = canvas.getContext('2d');

let lastTime = 0;

function gameLoop(timestamp) {
  const deltaTime = timestamp - lastTime;
  lastTime = timestamp;

  update(deltaTime);
  render();

  requestAnimationFrame(gameLoop);
}

requestAnimationFrame(gameLoop);
```

---

## P2: 入力ハンドリングパターン

```javascript
const input = {
  left: false,
  right: false,
  fire: false,
  mouseX: 0
};

// キーボード
document.addEventListener('keydown', e => {
  if (e.key === 'ArrowLeft' || e.key === 'a') input.left = true;
  if (e.key === 'ArrowRight' || e.key === 'd') input.right = true;
  if (e.key === ' ') input.fire = true;
});

document.addEventListener('keyup', e => {
  if (e.key === 'ArrowLeft' || e.key === 'a') input.left = false;
  if (e.key === 'ArrowRight' || e.key === 'd') input.right = false;
  if (e.key === ' ') input.fire = false;
});

// マウス
canvas.addEventListener('mousemove', e => {
  input.mouseX = e.clientX - canvas.offsetLeft;
});

canvas.addEventListener('click', () => {
  input.fire = true;
});
```

---

## P3: 当たり判定パターン（矩形）

```javascript
function checkCollision(a, b) {
  return (
    a.x < b.x + b.width &&
    a.x + a.width > b.x &&
    a.y < b.y + b.height &&
    a.y + a.height > b.y
  );
}
```

---

<!-- 新しいパターンはここに追加 -->
