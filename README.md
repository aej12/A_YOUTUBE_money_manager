<html lang="ko">
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: 'Pretendard', sans-serif;
      text-align: center;
      background-color: #f9f9f9;
      color: #333;
      padding: 20px;
    }
    h1 {
      color: #2a4d9b;
    }
    .notice {
      font-size: 13px;
      background-color: #fff;
      border-radius: 8px;
      padding: 10px;
      display: inline-block;
      box-shadow: 0 0 5px rgba(0,0,0,0.1);
      margin-bottom: 10px;
    }
    .ad-section {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
    }
    .btn {
      display: block;
      width: 220px;
      margin: 10px auto;
      padding: 12px;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      transition: 0.3s;
    }
    .btn:disabled {
      background-color: #aaa;
      cursor: not-allowed;
    }
    .btn-coupang {
      background-color: #007bff;
      color: #fff;
    }
    .btn-coupang:hover {
      background-color: #0062cc;
    }
    .btn-file {
      background-color: #28a745;
      color: #fff;
    }
    .btn-file:hover {
      background-color: #218838;
    }
    .group {
      margin: 25px 0;
    }
    .divider {
      margin: 30px auto;
      width: 60%;
      border-top: 2px dashed #ccc;
    }
  </style>
</head>
<body>
  <h1>A YOUTUBE money manager</h1>
  <div class="notice">
    본 페이지는 <strong>쿠팡파트너스</strong> 활동의 일환으로,<br>
    해당 링크를 통해 구매 시 일정액의 수수료를 제공받을 수 있습니다.<br>
    이 내용은 공정거래위원회의 ‘추천·보증 등에 관한 표시·광고 지침’을 준수합니다.
  </div>

  <div class="ad-section">📢 광고를 먼저 봐주세요!</div>
  <p>쿠팡 광고를 클릭하면 5초 후 가계부 자료가 열립니다.</p>

  <!-- ✅ 쿠팡 버튼 그룹 -->
  <div class="group">
    <button id="adBtn1" class="btn btn-coupang" onclick="activateFileBtn(1)">
      ✅ 쿠팡 인기상품 보기 (1번)
    </button>
    <p id="countdown1"></p>

    <button id="adBtn2" class="btn btn-coupang" onclick="activateFileBtn(2)">
      ✅ 쿠팡 인기상품 보기 (2번)
    </button>
    <p id="countdown2"></p>
  </div>

  <div class="divider"></div>

  <!-- ✅ 가계부 버튼 그룹 -->
  <div class="group">
    <button id="fileBtn1" class="btn btn-file" disabled>📄 1년 가계부 보기</button>
    <button id="fileBtn2" class="btn btn-file" disabled>📄 5년 가계부 보기</button>
  </div>

  <script>
    function activateFileBtn(num) {
      const countdownEl = document.getElementById(`countdown${num}`);
      const fileBtn = document.getElementById(`fileBtn${num}`);
      let timeLeft = 5;

      countdownEl.innerText = `⏳ ${timeLeft}초 후 버튼이 활성화됩니다...`;
      const timer = setInterval(() => {
        timeLeft--;
        countdownEl.innerText = `⏳ ${timeLeft}초 후 버튼이 활성화됩니다...`;
        if (timeLeft <= 0) {
          clearInterval(timer);
          countdownEl.innerText = `✅ ${num === 1 ? "1년" : "5년"} 가계부 버튼이 활성화되었습니다!`;
          fileBtn.disabled = false;
        }
      }, 1000);
    }

    // 가계부 링크 연결 (필요 시 수정)
    document.getElementById('fileBtn1').onclick = () => {
      window.open('https://example.com/1year-budget', '_blank');
    };
    document.getElementById('fileBtn2').onclick = () => {
      window.open('https://example.com/5year-budget', '_blank');
    };
  </script>
</body>
</html>
