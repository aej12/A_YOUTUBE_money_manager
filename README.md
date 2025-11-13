<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>A_YOUTUBE_money_manager</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      padding-top: 60px;
      background-color: #f9fafc;
    }

    .btn {
      display: block;
      width: 260px;
      padding: 15px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      margin: 15px auto;
      transition: all 0.3s ease;
    }

    .ad-button {
      background-color: #007aff;
      color: white;
    }

    .go-button {
      background-color: gray;
      color: white;
    }

    .go-button.active {
      background-color: #28a745;
    }

    .disclosure {
      font-size: 14px;
      color: #555;
      background-color: #f9f9f9;
      border: 1px solid #eee;
      border-radius: 8px;
      padding: 12px;
      width: fit-content;
      margin: 0 auto 40px auto;
      line-height: 1.5;
    }

    .timer {
      font-size: 15px;
      color: #666;
      margin-top: -5px;
      height: 20px;
    }
  </style>
</head>
<body>

  <!-- ✅ 공정위 문구 -->
  <div class="disclosure">
    본 페이지는 <strong>쿠팡파트너스 활동</strong>의 일환으로,<br>
    해당 링크를 통해 구매 시 <strong>일정액의 수수료를 제공받을 수 있습니다.</strong><br>
    이 내용은 <strong>공정거래위원회 ‘추천·보증 등에 관한 표시·광고 지침’</strong>을 준수합니다.
  </div>

  <h2>📢 광고를 먼저 봐주세요!</h2>
  <p>쿠팡 광고를 클릭하면 5초 후에 가계부 자료가 열립니다.</p>

  <!-- ✅ 쿠팡 광고 버튼 1 -->
  <a id="adLink1" href="https://link.coupang.com/a/cGwzg1" target="_blank" rel="noopener noreferrer">
    <button class="btn ad-button" type="button">✅ 쿠팡 인기상품 보기 (1번)</button>
  </a>
  <div id="timerMsg1" class="timer"></div>

  <!-- ✅ 쿠팡 광고 버튼 2 -->
  <a id="adLink2" href="https://link.coupang.com/a/cGwzg1" target="_blank" rel="noopener noreferrer">
    <button class="btn ad-button" type="button">✅ 쿠팡 인기상품 보기 (2번)</button>
  </a>
  <div id="timerMsg2" class="timer"></div>

  <!-- ✅ 공유자료 버튼 1 -->
  <button id="goBtn1" class="btn go-button" disabled>📄 1년 가계부 보기</button>

  <!-- ✅ 공유자료 버튼 2 -->
  <button id="goBtn2" class="btn go-button" disabled>📄 5년 가계부 보기</button>

  <script>
    // 버튼 요소들
    const adLink1 = document.getElementById("adLink1");
    const adLink2 = document.getElementById("adLink2");
    const goBtn1 = document.getElementById("goBtn1");
    const goBtn2 = document.getElementById("goBtn2");
    const timerMsg1 = document.getElementById("timerMsg1");
    const timerMsg2 = document.getElementById("timerMsg2");

    // ✅ 1번 쿠팡 버튼 클릭 시
    adLink1.addEventListener("click", () => {
      let countdown = 5;
      timerMsg1.textContent = `⏳ ${countdown}초 후 1년 가계부 버튼이 활성화됩니다.`;
      const interval = setInterval(() => {
        countdown--;
        if (countdown > 0) {
          timerMsg1.textContent = `⏳ ${countdown}초 후 1년 가계부 버튼이 활성화됩니다.`;
        } else {
          clearInterval(interval);
          timerMsg1.textContent = "✅ 1년 가계부 버튼이 활성화되었습니다!";
          goBtn1.disabled = false;
          goBtn1.classList.add("active");
        }
      }, 1000);
    });

    // ✅ 2번 쿠팡 버튼 클릭 시
    adLink2.addEventListener("click", () => {
      let countdown = 5;
      timerMsg2.textContent = `⏳ ${countdown}초 후 5년 가계부 버튼이 활성화됩니다.`;
      const interval = setInterval(() => {
        countdown--;
        if (countdown > 0) {
          timerMsg2.textContent = `⏳ ${countdown}초 후 5년 가계부 버튼이 활성화됩니다.`;
        } else {
          clearInterval(interval);
          timerMsg2.textContent = "✅ 5년 가계부 버튼이 활성화되었습니다!";
          goBtn2.disabled = false;
          goBtn2.classList.add("active");
        }
      }, 1000);
    });

    // ✅ 구글시트 링크 연결
    goBtn1.addEventListener("click", () => {
      window.location.href = "https://docs.google.com/spreadsheets/d/1vsANf1UP_TJUDsJKnUEme-G88ggJf4yUJi_ttHPJkx0/edit?gid=741215701#gid=741215701";
    });

    goBtn2.addEventListener("click", () => {
      window.location.href = "https://docs.google.com/spreadsheets/d/18NJ6G2lvuQ1xUCHTQ8vBaqtRY20LEk496am42yybhqw/edit?gid=0#gid=0";
    });
  </script>

</body>
</html>
