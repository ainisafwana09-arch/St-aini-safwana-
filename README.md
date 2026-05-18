<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Persahabatan Erat</title>

  <style>
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      font-family: Arial, sans-serif;
    }

    body{
      height:100vh;
      display:flex;
      justify-content:center;
      align-items:center;
      background: linear-gradient(135deg, #7b2cbf, #9d4edd);
      overflow:hidden;
    }

    .container{
      text-align:center;
      color:white;
      padding:30px;
    }

    h1{
      margin-bottom:15px;
      font-size:40px;
    }

    p{
      margin-bottom:25px;
      font-size:18px;
    }

    .heart-btn{
      width:120px;
      height:120px;
      background:#ff4d8d;
      position:relative;
      transform:rotate(-45deg);
      margin:20px auto;
      cursor:pointer;
      transition:0.3s;
      animation: pulse 1.5s infinite;
    }

    .heart-btn::before,
    .heart-btn::after{
      content:'';
      width:120px;
      height:120px;
      background:#ff4d8d;
      border-radius:50%;
      position:absolute;
    }

    .heart-btn::before{
      top:-60px;
      left:0;
    }

    .heart-btn::after{
      left:60px;
      top:0;
    }

    .heart-btn:hover{
      transform:rotate(-45deg) scale(1.1);
    }

    @keyframes pulse{
      0%{
        transform:rotate(-45deg) scale(1);
      }
      50%{
        transform:rotate(-45deg) scale(1.08);
      }
      100%{
        transform:rotate(-45deg) scale(1);
      }
    }

    .question{
      display:none;
      margin-top:30px;
    }

    .question h2{
      margin-bottom:20px;
    }

    button{
      padding:12px 28px;
      margin:10px;
      border:none;
      border-radius:12px;
      font-size:18px;
      cursor:pointer;
      transition:0.3s;
      font-weight:bold;
    }

    .yes{
      background:#ff69b4;
      color:white;
    }

    .yes:hover{
      background:#ff85c1;
      transform:scale(1.1);
    }

    .no{
      background:#444;
      color:white;
    }

    .no:hover{
      background:#666;
      transform:scale(1.1);
    }

    .result{
      margin-top:30px;
      font-size:60px;
      min-height:80px;
      animation: fade 0.5s ease;
    }

    @keyframes fade{
      from{
        opacity:0;
        transform:translateY(20px);
      }
      to{
        opacity:1;
        transform:translateY(0);
      }
    }

  </style>
</head>
<body>

  <div class="container">
    <h1>💜 Persahabatan Erat 💜</h1>
    <p>Tekan hati pink untuk memulai</p>

    <div class="heart-btn" id="heart"></div>

    <div class="question" id="questionBox">
      <h2>Apakah persahabatan kita akan selalu erat?</h2>

      <button class="yes" onclick="showLove()">YA</button>
      <button class="no" onclick="showFire()">TIDAK</button>

      <div class="result" id="result"></div>
    </div>
  </div>

  <script>
    const heart = document.getElementById("heart");
    const questionBox = document.getElementById("questionBox");
    const result = document.getElementById("result");

    heart.addEventListener("click", () => {
      questionBox.style.display = "block";
      heart.style.display = "none";
    });

    function showLove(){
      result.innerHTML = "💖 💕 💗 💞";
    }

    function showFire(){
      result.innerHTML = "🔥 🔥 🔥";
    }
  </script>

</body>
</html>
