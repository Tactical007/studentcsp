---
layout: base
title: Student Home 
description: Home Page
hide: true
---

## My name is Luke Starr

<p
style="font-family:'cascadia-code'!important; "> My journey starts here. Hello im Luke and this is my homepage!</p>

<div style="border: 2px solid black; padding: 10px; margin-bottom: 20px;">
<p>These are just a couple of photos from some personal projects I took.</p>
  <button
style="background-color: #FF0000 !important; font-family: 'open sans' , sans-serif !important; "> click for nothing! 
</button>
  <div style="font-weight: bold; font-size: 24px; display: inline-block; margin: 10px;">buttons!</div>
</div>

<div style="border: 2px solid black; padding: 10px; background-color: #316362 !important">
  <a href="https://i.imgur.com/8kcMHPT.png" style="border: 2px solid black; display: block; padding: 10px; margin: 10px; color: green; font-weight: bold; text-align: center; text-decoration: none;">click?</a>
   <a href="https://i.imgur.com/E2dDMVi.png" style="border: 2px solid black; display: block; padding: 10px; margin: 10px; color: green; font-weight: bold; text-align: center; text-decoration: none;">click for part of my  personal project</a>
  <a href="https://brycemironuck.com/wp-content/uploads/2023/05/scripps-pier-la-jolla-lg.jpg" style="border: 2px solid black; display: block; padding: 10px; margin: 10px; color: red; font-weight: bold; text-align: center; text-decoration: none;">click to see a pier</a>
  
  <script>
    function funButton() {
    alert ("thank you for clicking!")
    }
</script>
<p style="text-align: left;">
    <button style="padding:10px 20px; background-colorL#000000; color:black !important; border:thin border-radius:50px; font-family:'avalon'!important; "
    button onClick= "funButton()">
        Click?
    </button>
</p>
<p>Hi this is my first try at making this format! Thanks for looking at it! Have a good rest of your day:></p>
</div>

<img id="Mario" src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/e8e1555a-b50a-4eac-9515-647481d25076/ddy2owj-c064c23e-d4a4-4f03-8816-2566b2a604c2.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcL2U4ZTE1NTVhLWI1MGEtNGVhYy05NTE1LTY0NzQ4MWQyNTA3NlwvZGR5Mm93ai1jMDY0YzIzZS1kNGE0LTRmMDMtODgxNi0yNTY2YjJhNjA0YzIuZ2lmIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.NY2XmAD27Qu-GWx_wRJoTDdmXiHTjm1xWA5rfnUC6Dk" 
alt="mario" style="width:130px; position:absolute; bottom:0; left:0;">

<script>
  function moveMario() {
    var mario = document.getElementById("Mario");
    var position = 0;
    var speed = 3; 
    var interval = setInterval(function() {
      if (position >= window.innerWidth) {
        position = -13;
      } else {
        position += speed;
        mario.style.left = position + "px";
      }
    }, 10);
  }
  
  moveMario();
</script>

<img id="Bowser" src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/4d115b6d-27dd-4f7f-b2b2-151e9165d090/dc9qpkc-1ea9ade7-d144-4f5c-83fe-b25a4e8bb210.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzRkMTE1YjZkLTI3ZGQtNGY3Zi1iMmIyLTE1MWU5MTY1ZDA5MFwvZGM5cXBrYy0xZWE5YWRlNy1kMTQ0LTRmNWMtODNmZS1iMjVhNGU4YmIyMTAuZ2lmIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.MxMN4rxGAfsgI02R2LMdqkeZfIi21FMIlE9P5REfxuY" 
alt="Bowser" style="width:260px; position:absolute; bottom:0; left:0;">

<script>
  function moveBowser() {
    var bowser = document.getElementById("Bowser");
    var position = 0;
    var speed = 5; 
    var interval = setInterval(function() {
      if (position >= window.innerWidth) {
        position = -130;
      } else {
        position += speed;
        bowser.style.left = position + "px";
      }
    }, 10);
  }
  
  moveBowser();
</script>

<img id="Mario" src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/e8e1555a-b50a-4eac-9515-647481d25076/ddy2owj-c064c23e-d4a4-4f03-8816-2566b2a604c2.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcL2U4ZTE1NTVhLWI1MGEtNGVhYy05NTE1LTY0NzQ4MWQyNTA3NlwvZGR5Mm93ai1jMDY0YzIzZS1kNGE0LTRmMDMtODgxNi0yNTY2YjJhNjA0YzIuZ2lmIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.NY2XmAD27Qu-GWx_wRJoTDdmXiHTjm1xWA5rfnUC6Dk" 
alt="mario" style="width:130px; position:absolute; bottom:0; left:0;">