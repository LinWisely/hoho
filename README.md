<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>鍵盤按鍵偵測器</title>
  <style>
    body {
      font-family: "Microsoft JhengHei", sans-serif;
      background: #f0f2f5;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }
    h1 {
      color: #333;
    }
    #output {
      background: white;
      padding: 1.5em 2em;
      border-radius: 8px;
      border: 1px solid #ccc;
      margin-top: 1em;
      font-size: 1.5em;
      min-width: 300px;
      text-align: center;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
  </style>
</head>
<body>

  <h1>🔍 鍵盤偵測器</h1>
  <p>請在網頁上按任何鍵，我會顯示你按下了什麼：</p>
  <div id="output">尚未按鍵</div>

  <script>
    const output = document.getElementById("output");

    document.addEventListener("keydown", function(event) {
      const key = event.key;
      const code = event.code;
      const ctrl = event.ctrlKey ? "Ctrl+" : "";
      const alt = event.altKey ? "Alt+" : "";
      const shift = event.shiftKey ? "Shift+" : "";
      output.textContent = `你按下了：${ctrl}${alt}${shift}${key}（代碼：${code}）`;
    });
  </script>

</body>
</html>
