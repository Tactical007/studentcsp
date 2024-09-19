---
layout: page
title: Tic-Tack-Toe
permalink: /tictacktoe/
---

<div style="max-width: 300px; margin: 0 auto;">
  <h2 style="text-align: center;">Tic-Tac-Toe</h2>
  <div id="ticTacToeBoard" style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 5px;">
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(0)"></div>
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(1)"></div>
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(2)"></div>
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(3)"></div>
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(4)"></div>
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(5)"></div>
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(6)"></div>
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(7)"></div>
    <div style="width: 100px; height: 100px; display: flex; justify-content: center; align-items: center; background-color: #f4f4f4; font-size: 2rem; cursor: pointer;" onclick="makeMove(8)"></div>
  </div>
  <h3 id="status" style="text-align: center; margin-top: 20px;"></h3>
</div>

<script>
  let board = ['', '', '', '', '', '', '', '', ''];
  let currentPlayer = 'X';
  let gameActive = true;

  function makeMove(index) {
    if (board[index] === '' && gameActive) {
      board[index] = currentPlayer;
      document.querySelectorAll('#ticTacToeBoard div')[index].textContent = currentPlayer;
      checkWinner();
      currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
      document.getElementById('status').textContent = `${currentPlayer}'s turn`;
    }
  }

  function checkWinner() {
    const winningCombinations = [
      [0, 1, 2], [3, 4, 5], [6, 7, 8], // rows
      [0, 3, 6], [1, 4, 7], [2, 5, 8], // columns
      [0, 4, 8], [2, 4, 6]             // diagonals
    ];

    for (const combination of winningCombinations) {
      const [a, b, c] = combination;
      if (board[a] && board[a] === board[b] && board[a] === board[c]) {
        gameActive = false;
        showResult(`${board[a]} wins!`);
        return;
      }
    }

    if (!board.includes('')) {
      gameActive = false;
      showResult("It's a tie!");
    }
  }

  function showResult(message) {
    alert(message);
  }

  function resetGame() {
    board = ['', '', '', '', '', '', '', '', ''];
    document.querySelectorAll('#ticTacToeBoard div').forEach(cell => cell.textContent = '');
    currentPlayer = 'X';
    gameActive = true;
    document.getElementById('status').textContent = "X's turn";
  }
</script>

<button style="display: block; margin: 20px auto; padding: 10px 20px; font-size: 1rem;" onclick="resetGame()">Restart Game</button>


<script src="https://utteranc.es/client.js"
        repo="studentcsp"
        issue-term="title"
        label="blogpost-comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>