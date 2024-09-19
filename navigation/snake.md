---
layout: page
title: Snake
permalink: /snake/
---


<div style="max-width: 500px; margin: 0 auto;">
  <canvas id="snakeGame" style="border: 1px solid #000; background-color: #f4f4f4;"></canvas>
</div>

<script>
  const canvas = document.getElementById('snakeGame');
  const ctx = canvas.getContext('2d');
  const grid = 20;
  let count = 0;
  let snake = [{ x: 160, y: 160 }];
  let apple = { x: 80, y: 80 };
  let dx = grid;
  let dy = 0;
  let growing = false;

  function getRandomInt(max) {
    return Math.floor(Math.random() * max) * grid;
  }

  function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = 'green';
    snake.forEach(part => ctx.fillRect(part.x, part.y, grid, grid));
    
    ctx.fillStyle = 'red';
    ctx.fillRect(apple.x, apple.y, grid, grid);
  }

  function move() {
    const head = { x: snake[0].x + dx, y: snake[0].y + dy };
    snake.unshift(head);
    
    if (head.x === apple.x && head.y === apple.y) {
      apple.x = getRandomInt(canvas.width / grid);
      apple.y = getRandomInt(canvas.height / grid);
      growing = true;
    }
    
    if (!growing) {
      snake.pop();
    } else {
      growing = false;
    }
  }

  function checkCollision() {
    if (snake[0].x < 0 || snake[0].x >= canvas.width || snake[0].y < 0 || snake[0].y >= canvas.height) {
      return true;
    }

    for (let i = 1; i < snake.length; i++) {
      if (snake[0].x === snake[i].x && snake[0].y === snake[i].y) {
        return true;
      }
    }

    return false;
  }

  function gameLoop() {
    if (checkCollision()) {
      alert('Game Over');
      snake = [{ x: 160, y: 160 }];
      dx = grid;
      dy = 0;
      apple = { x: getRandomInt(canvas.width / grid), y: getRandomInt(canvas.height / grid) };
    }

    count++;
    if (count > 5) {
      move();
      count = 0;
    }

    draw();
  }

  document.addEventListener('keydown', e => {
    if (e.key === 'ArrowUp' && dy === 0) {
      dx = 0;
      dy = -grid;
    }
    if (e.key === 'ArrowDown' && dy === 0) {
      dx = 0;
      dy = grid;
    }
    if (e.key === 'ArrowLeft' && dx === 0) {
      dx = -grid;
      dy = 0;
    }
    if (e.key === 'ArrowRight' && dx === 0) {
      dx = grid;
      dy = 0;
    }
  });

  canvas.width = 400;
  canvas.height = 400;
  setInterval(gameLoop, 100);
</script>