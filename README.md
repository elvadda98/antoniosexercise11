<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Fill in the Blanks</title>
  <style>
    body { font-family: Arial; text-align: center; padding: 20px; }
    input { padding: 10px; margin: 10px; font-size: 18px; }
  </style>
</head>
<body>
  <h1>Fill in the Blank</h1>
  <div id="sentence"></div>
  <input id="answer" placeholder="Type word">
  <button onclick="checkAnswer()">Check</button>
  <div id="result"></div>

  <script>
    const words = ["sunrise","rent","expensive","savory","buy","foreign","well","mistake","sunset",
    "behave","came to mind","came up","moan","hard","roommate","rooted","beginning","same","main",
    "train","amount","hold back","quick","screen","middle","replacement","improvement","busy","keep",
    "usual","staff","find","basically","brake up"];

    let currentWord = "";
    function newSentence() {
      currentWord = words[Math.floor(Math.random()*words.length)];
      document.getElementById("sentence").innerText = "Use the word: ____ ("+ currentWord.length +" letters)";
      document.getElementById("answer").value = "";
      document.getElementById("result").innerText = "";
    }
    function checkAnswer() {
      const ans = document.getElementById("answer").value.trim().toLowerCase();
      if(ans === currentWord) document.getElementById("result").innerText = "✅ Correct!";
      else document.getElementById("result").innerText = "❌ Try again! It was: " + currentWord;
      setTimeout(newSentence, 1500);
    }
    newSentence();
  </script>
</body>
</html>
