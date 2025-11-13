
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <style>
    body {
      font-family: "Pretendard", sans-serif;
      text-align: center;
      background-color: #f9f9f9;
      color: #333;
      padding: 20px;
      line-height: 1.5;
    }
    h1 {
      color: #2a4d9b;
      font-size: 26px;
      margin-bottom: 10px;
    }
    .notice {
      background: #fff;
      border-radius: 10px;
      padding: 15px;
      margin: 15px auto;
      display: inline-block;
      font-size: 14px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
    }
    .ad-section {
      font-weight: bold;
      font-size: 18px;
      margin-top: 25px;
    }
    .btn {
      display: block;
      width: 240px;
      margin: 12px auto;
      padding: 13px 0;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    .btn:disabled {
      opacity: 0.6;
      cursor: not-allowed;
    }
    .btn-coupang {
      background-color: #007bff;
      color: white;
    }
    .btn-coupang:hover {
      background-color: #005fcc;
    }
    .btn-file {
      background-color: #28a745;
      color: white;
    }
    .btn-file:hover {
      background-color: #1f7a36;
    }
    .divider {
      margin: 30px auto;
      width: 60%;
      border-top: 2px dashed #ccc;
    }
    p.countdown {
      font-size: 14px;
      color: #555;
      margin: 5px 0 15px;
    }
  </style>
</head>
<body>


  <div class="notice">
    본 페이지는 <strong>쿠팡파트너스</strong> 활동의 일환으로,<br>
    해당 링크를 통해 구매 시 일정액의 수수료를 제공받을 수 있습니다.<br>
    이 내용은 공정거래위원회의 ‘추천·보증 등에 관한 표시·광고 지침’을 준수합니다.
  </div>

  <div class="ad-section">📢 광고를 먼저 봐주세요!</div>
  <p>쿠팡 광고를 클릭하면 5초 후 가계부 자료가 열립니다.</p>

  <!-- ✅ 쿠팡 1 + 1년 가계부 -->
  <button id="adBtn1" class="btn btn-coupang">✅ 쿠팡 인기상품 보기 (1번)</button>
  <p id="countdown1" class="countdown"></p>
  <button id="fileBtn1" class="btn btn-file" disabled>📄 1년 가계부 보기</button>

  <div class="divider"></div>

  <!-- ✅ 쿠팡 2 + 5년 가계부 -->
  <button id="adBtn2" class="btn btn-coupang">✅ 쿠팡 인기상품 보기 (2번)</button>
  <p id="countdown2" class="countdown"></p>
  <button id="fileBtn2" class="btn btn-file" disabled>📄 5년 가계부 보기</button>

  <script>
    function startCountdown(adNum, coupangUrl, fileBtnId, countdownId) {
      const countdown = document.getElementById(countdownId);
      const fileBtn = document.getElementById(fileBtnId);
      let seconds = 5;

      // 쿠팡 링크 열기 (모바일에서도 새창 인식되도록 window.open 사용)
      window.open(coupangUrl, "_blank");

      countdown.textContent = `⏳ ${seconds}초 후 버튼이 활성화됩니다...`;

      const timer = setInterval(() => {
        seconds--;
        countdown.textContent = `⏳ ${seconds}초 후 버튼이 활성화됩니다...`;

        if (seconds <= 0) {
          clearInterval(timer);
          countdown.textContent = `✅ 버튼이 활성화되었습니다!`;
          fileBtn.disabled = false;
        }
      }, 1000);
    }

    // ✅ 버튼 이벤트 연결
    document.getElementById("adBtn1").addEventListener("click", () => {
      startCountdown(1, "https://www.coupang.com/np/goldbox", "fileBtn1", "countdown1");
    });

    document.getElementById("adBtn2").addEventListener("click", () => {
      startCountdown(2, "https://www.coupang.com/np/goldbox", "fileBtn2", "countdown2");
    });

    // ✅ 가계부 링크 연결
    document.getElementById("fileBtn1").onclick = () => {
      window.open("https://docs.google.com/spreadsheets/d/1vsANf1UP_TJUDsJKnUEme-G88ggJf4yUJi_ttHPJkx0/edit?gid=741215701#gid=741215701", "_blank");
    };
    document.getElementById("fileBtn2").onclick = () => {
      window.open("https://docs.google.com/spreadsheets/d/18NJ6G2lvuQ1xUCHTQ8vBaqtRY20LEk496am42yybhqw/edit?gid=0#gid=0", "_blank");
    };
  </script>
</body>
</html>
