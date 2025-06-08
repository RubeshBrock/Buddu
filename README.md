<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday Buddu!</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: linear-gradient(135deg, #ffd1dc, #e0bbff);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      overflow: hidden;
    }

    .unicorn {
      position: relative;
      width: 200px;
      height: 200px;
      background: url('https://media.giphy.com/media/Sy3l0d6TgfYbW/giphy.gif') no-repeat center/contain;
    }

    .bubble {
      position: absolute;
      top: -60px;
      left: 50%;
      transform: translateX(-50%);
      background: white;
      border-radius: 15px;
      padding: 15px;
      max-width: 300px;
      font-size: 1em;
      box-shadow: 2px 2px 10px rgba(0,0,0,0.2);
      animation: bounce 1s infinite alternate;
    }

    @keyframes bounce {
      from { transform: translate(-50%, 0); }
      to { transform: translate(-50%, -10px); }
    }

    .input-area {
      margin-top: 20px;
      text-align: center;
    }

    input {
      padding: 10px;
      font-size: 1em;
      border: 2px solid #ccc;
      border-radius: 10px;
      width: 250px;
      margin-top: 10px;
    }

    button {
      margin-top: 15px;
      padding: 10px 20px;
      background: #ff69b4;
      color: white;
      border: none;
      border-radius: 10px;
      font-size: 1em;
      cursor: pointer;
    }

    .message-box {
      display: none;
      margin-top: 30px;
      text-align: center;
      background: rgba(255, 255, 255, 0.9);
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
    }

    .message-box h1 {
      color: #d63384;
    }
  </style>
</head>
<body>

  <div class="unicorn">
    <div class="bubble" id="bubbleText">Hi! What’s your name? 🦄</div>
  </div>

  <div class="input-area">
    <input type="text" id="usernameInput" placeholder="Enter Username" />
    <input type="password" id="passwordInput" placeholder="Enter Password" style="display:none;" />
    <button onclick="handleNext()" id="nextBtn">Next</button>
  </div>

  <div class="message-box" id="messageBox">
    <h1>🎉 Happy Birthday Buddu Buddu Shree! 🎉</h1>
    <p>Wishing you sparkly magic, joy, and unicorn dreams come true! 🦄💖</p>
  </div>

  <script>
    let step = 1;

    function handleNext() {
      const username = document.getElementById('usernameInput').value;
      const password = document.getElementById('passwordInput').value;
      const bubble = document.getElementById('bubbleText');

      if (step === 1) {
        if (username === '') {
          alert('Please enter a username!');
          return;
        }
        bubble.textContent = `Nice to meet you, ${username}! What's the password? 🔐`;
        document.getElementById('usernameInput').style.display = 'none';
        document.getElementById('passwordInput').style.display = 'block';
        step = 2;
      } else if (step === 2) {
        if (password === '') {
          alert('Please enter the password!');
          return;
        }
        if (username === 'Buddu' && password === '29081999') {
          document.querySelector('.unicorn').style.display = 'none';
          document.querySelector('.input-area').style.display = 'none';
          document.getElementById('messageBox').style.display = 'block';
        } else {
          alert('Wrong username or password! 🛑');
        }
      }
    }
  </script>

</body>
</html>
