<html>
<head>
  <title>Efficiency Ratios Quiz</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    .question { margin-bottom: 20px; }
    .result { margin-top: 20px; font-weight: bold; }
    .suggestion { color: green; }
    .wrong { color: red; }
  </style>
</head>
<body>

<h2>Efficiency Ratios Quiz</h2>

<form id="quizForm">
  <div class="question">
    <p>1. A company has net credit sales of ₹12,00,000 and average accounts receivable of ₹2,00,000. What is the Debtor Turnover Ratio?</p>
    <input type="radio" name="q1" value="A"> A. 4 times<br>
    <input type="radio" name="q1" value="B"> B. 5 times<br>
    <input type="radio" name="q1" value="C"> C. 6 times<br>
    <input type="radio" name="q1" value="D"> D. 8 times<br>
  </div>

  <div class="question">
    <p>2. Which of the following best describes a low Inventory Turnover Ratio?</p>
    <input type="radio" name="q2" value="A"> A. High sales and efficient stock control<br>
    <input type="radio" name="q2" value="B"> B. Inefficient inventory management and overstocking<br>
    <input type="radio" name="q2" value="C"> C. Rapid inventory movement<br>
    <input type="radio" name="q2" value="D"> D. Good working capital control<br>
  </div>

  <div class="question">
    <p>3. A high Working Capital Turnover Ratio (WCTR) usually means:</p>
    <input type="radio" name="q3" value="A"> A. Efficient use of working capital in generating sales<br>
    <input type="radio" name="q3" value="B"> B. Excess working capital<br>
    <input type="radio" name="q3" value="C"> C. High investment in fixed assets<br>
    <input type="radio" name="q3" value="D"> D. Poor sales performance<br>
  </div>

  <div class="question">
    <p>4. If a firm’s average accounts payable is ₹1,50,000 and net credit purchases are ₹9,00,000, what is the Creditor Turnover Ratio?</p>
    <input type="radio" name="q4" value="A"> A. 4 times<br>
    <input type="radio" name="q4" value="B"> B. 5 times<br>
    <input type="radio" name="q4" value="C"> C. 7 times<br>
    <input type="radio" name="q4" value="D"> D. 6 times<br>
  </div>

  <div class="question">
    <p>5. Which scenario is most likely if Debtor Turnover Ratio decreases significantly?</p>
    <input type="radio" name="q5" value="A"> A. Better cash management<br>
    <input type="radio" name="q5" value="B"> B. Collection period has increased, affecting liquidity<br>
    <input type="radio" name="q5" value="C"> C. Sales have improved<br>
    <input type="radio" name="q5" value="D"> D. Debtors are being paid faster<br>
  </div>

  <button type="button" onclick="checkAnswers()">Submit Answers</button>
</form>

<div id="result" class="result"></div>

<script>
function checkAnswers() {
  const answers = {
    q1: "C",
    q2: "B",
    q3: "A",
    q4: "D",
    q5: "B"
  };

  let score = 0;
  let resultText = "";
  let suggestions = "";

  for (let i = 1; i <= 5; i++) {
    const q = document.querySelector(`input[name="q${i}"]:checked`);
    if (q) {
      if (q.value === answers[`q${i}`]) {
        score++;
      } else {
        suggestions += `<p class="wrong">Question ${i}: Incorrect. <br><span class="suggestion">Suggested: ${getSuggestion(i)}</span></p>`;
      }
    } else {
      suggestions += `<p class="wrong">Question ${i}: Not answered.</p>`;
    }
  }

  resultText = `<p>Your Score: ${score}/5</p>`;
  document.getElementById("result").innerHTML = resultText + suggestions;
}

function getSuggestion(qNum) {
  switch (qNum) {
    case 1:
      return "Debtor Turnover Ratio = Net Credit Sales / Average Receivables. So, 12,00,000 / 2,00,000 = 6.";
    case 2:
      return "Low ITR means stock is moving slowly, which may indicate poor sales or overstocking.";
    case 3:
      return "High WCTR means the firm is efficiently using working capital to generate revenue.";
    case 4:
      return "CTR = Net Credit Purchases / Average Payables = 9,00,000 / 1,50,000 = 6.";
    case 5:
      return "Falling DTR means slow debtor collection, increasing the risk of bad debts and liquidity issues.";
  }
}
</script>

</body>
</html>
