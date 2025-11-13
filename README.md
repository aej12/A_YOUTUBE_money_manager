<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>광고 시청 후 자료 보기</title>
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
      font-size: 14px;
      color: #666;
      margin-top: -10px;
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
  <p>쿠팡 광고를 클릭하면 일정 시간 후 공유자료가 열립니다.</p>

  <!-- ✅ 쿠팡 광고 버튼 -->
  <a id="adLink" href="https://link.coupang.com/a/cGwzg1" target="_blank" rel="noopener noreferrer">
    <button class="btn ad-button" type="button">✅ 쿠팡 인기 상품 보기</button>
  </a>

  <!-- 타이머 문구 -->
  <div id="timerMsg" class="timer"></div>

  <!-- 공유자료 버튼 1 (1년 가계부) -->
  <button id="goBtn1" class="btn go-button" disabled>📄 1년 가계부 보기</button>

  <!-- 공유자료 버튼 2 (5년 가계부) -->
  <button id="goBtn2" class="btn go-button" disabled>📄 5년 가계부 보기</button>

  <script>
    const adLink = document.getElementById("adLink");
    const goBtn1 = document.getElementById("goBtn1");
    const goBtn2 = document.getElementById("goBtn2");
    const timerMsg = document.getElementById("timerMsg");

    let clickCount = 0; // 쿠팡버튼 클릭횟수 추적

    adLink.addEventListener("click", (event) => {
      clickCount++;

      // 쿠팡 링크 새 창에서 열기 유지
      setTimeout(() => {
        if (clickCount === 1) {
          timerMsg.textContent = "⏳ 5초 후 ‘1년 가계부 보기’ 버튼이 활성화됩니다...";
          setTimeout(() => {
            goBtn1.disabled = false;
            goBtn1.classList.add("active");
            timerMsg.textContent = "✅ 1년 가계부 버튼이 활성화되었습니다!";
          }, 5000);
        } else if (clickCount === 2) {
          timerMsg.textContent = "⏳ 5초 후 ‘5년 가계부 보기’ 버튼이 활성화됩니다...";
          setTimeout(() => {
            goBtn2.disabled = false;
            goBtn2.classList.add("active");
            timerMsg.textContent = "✅ 5년 가계부 버튼이 활성화되었습니다!";
          }, 5000);
        } else {
          timerMsg.textContent = "모든 가계부가 이미 활성화되었습니다 ✅";
        }
      }, 500);
    });

    // ✅ 링크 연결
    goBtn1.addEventListener("click", () => {
      window.location.href = "https://docs.google.com/spreadsheets/d/1vsANf1UP_TJUDsJKnUEme-G88ggJf4yUJi_ttHPJkx0/edit?gid=741215701#gid=741215701";
    });

    goBtn2.addEventListener("click", () => {
      window.location.href = "https://docs.google.com/spreadsheets/d/18NJ6G2lvuQ1xUCHTQ8vBaqtRY20LEk496am42yybhqw/edit?gid=0#gid=0";
    });
  </script>

</body>
</html>
