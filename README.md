<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Quiz Timer</title>
  <style>
    body {
      font-family: sans-serif;
      background-color: #f9fafb;
      padding: 2rem;
    }
    .progress-container {
      height: 8px;
      background-color: #e5e7eb; /* gray-200 */
      border-radius: 9999px;
      overflow: hidden;
      width: 100%;
      max-width: 600px;
      margin: 2rem auto;
    }
    .progress-bar {
      height: 100%;
      width: 100%;
      background-color: #3b82f6; /* blue-500 */
      border-radius: 9999px;
      transition: width 1s linear;
    }
  </style>
</head>
<body>

  <h1 style="text-align: center;">Quiz Timer</h1>
  <div class="progress-container">
    <div id="progressBar" class="progress-bar"></div>
  </div>

  <script>
    const TOTAL_TIME = 15; // seconds
    let timeLeft = TOTAL_TIME;
    const progressBar = document.getElementById('progressBar');

    const interval = setInterval(() => {
      timeLeft--;

      const widthPercentage = (timeLeft / TOTAL_TIME) * 100;
      progressBar.style.width = widthPercentage + '%';

      if (timeLeft <= 0) {
        clearInterval(interval);
        alert("Time's up!");
      }
    }, 1000);
  </script>
</body>
</html>
