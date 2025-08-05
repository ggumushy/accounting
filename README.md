<!DOCTYPE html>
<html>
<head>
  <title>Accounting Quiz: Balance Sheet, Current Ratio & Accounting Equation</title>
  <style>
    body {
      font-family: Arial;
      margin: 30px;
    }
    .question {
      margin-bottom: 20px;
    }
    textarea {
      width: 100%;
      height: 80px;
    }
    button {
      padding: 10px 20px;
      margin-top: 20px;
    }
    .result {
      margin-top: 30px;
      background-color: #f0f8ff;
      padding: 20px;
      border: 1px solid #ccc;
    }
  </style>
</head>
<body>

  <h1>Accounting Quiz</h1>
  <form id="quizForm">

    <!-- MCQ Questions -->
    <div class="question">
      <p><b>1. What does the accounting equation represent?</b></p>
      <input type="radio" name="q1" value="A"> A. Assets = Revenue - Liabilities<br>
      <input type="radio" name="q1" value="B"> B. Assets = Liabilities + Owner's Equity<br>
      <input type="radio" name="q1" value="C"> C. Assets = Liabilities - Equity<br>
      <input type="radio" name="q1" value="D"> D. Assets = Expenses + Revenue<br>
    </div>

    <div class="question">
      <p><b>2. Which of the following is a current asset?</b></p>
      <input type="radio" name="q2" value="A"> A. Land<br>
      <input type="radio" name="q2" value="B"> B. Machinery<br>
      <input type="radio" name="q2" value="C"> C. Inventory<br>
      <input type="radio" name="q2" value="D"> D. Patents<br>
    </div>

    <div class="question">
      <p><b>3. What does a current ratio of less than 1 indicate?</b></p>
      <input type="radio" name="q3" value="A"> A. Strong liquidity position<br>
      <input type="radio" name="q3" value="B"> B. Solvency issues<br>
      <input type="radio" name="q3" value="C"> C. Short-term liabilities exceed current assets<br>
      <input type="radio" name="q3" value="D"> D. Company has no liabilities<br>
    </div>

    <div class="question">
      <p><b>4. Which item appears on a balance sheet?</b></p>
      <input type="radio" name="q4" value="A"> A. Sales revenue<br>
      <input type="radio" name="q4" value="B"> B. Cost of goods sold<br>
      <input type="radio" name="q4" value="C"> C. Accounts payable<br>
      <input type="radio" name="q4" value="D"> D. Rent expense<br>
    </div>

    <div class="question">
      <p><b>5. If assets are ₹2,00,000 and liabilities are ₹1,20,000, what is equity?</b></p>
      <input type="radio" name="q5" value="A"> A. ₹80,000<br>
      <input type="radio" name="q5" value="B"> B. ₹3,20,000<br>
      <input type="radio" name="q5" value="C"> C. ₹1,20,000<br>
      <input type="radio" name="q5" value="D"> D. ₹2,80,000<br>
    </div>

    <div class="question">
      <p><b>6. What is the ideal current ratio generally recommended?</b></p>
      <input type="radio" name="q6" value="A"> A. 1:1<br>
      <input type="radio" name="q6" value="B"> B. 3:1<br>
      <input type="radio" name="q6" value="C"> C. 2:1<br>
      <input type="radio" name="q6" value="D"> D. 0.5:1<br>
    </div>

    <div class="question">
      <p><b>7. Which of the following transactions increases both assets and liabilities?</b></p>
      <input type="radio" name="q7" value="A"> A. Purchase of inventory with cash<br>
      <input type="radio" name="q7" value="B"> B. Taking a loan from bank<br>
      <input type="radio" name="q7" value="C"> C. Depreciation on machinery<br>
      <input type="radio" name="q7" value="D"> D. Owner's capital investment<br>
    </div>

    <!-- Subjective Questions -->
    <div class="question">
      <p><b>8. Explain the importance of current ratio in financial analysis.</b></p>
      <textarea name="sub1" placeholder="Write your answer here..."></textarea>
    </div>

    <div class="question">
      <p><b>9. What are the limitations of the balance sheet?</b></p>
      <textarea name="sub2" placeholder="Write your answer here..."></textarea>
    </div>

    <div class="question">
      <p><b>10. How does the accounting equation help in double-entry bookkeeping?</b></p>
      <textarea name="sub3" placeholder="Write your answer here..."></textarea>
    </div>

    <button type="button" onclick="calculateResult()">Submit</button>

    <!-- Result Section -->
    <div class="result" id="result" style="display:none;"></div>

  </form>

  <script>
    const answers = {
      q1: 'B',
      q2: 'C',
      q3: 'C',
      q4: 'C',
      q5: 'A',
      q6: 'C',
      q7: 'B'
    };

    function calculateResult() {
      let score = 0;
      let total = 70;
      for (let i = 1; i <= 7; i++) {
        let q = document.querySelector(`input[name="q${i}"]:checked`);
        if (q && q.value === answers["q" + i]) {
          score += 10;
        }
      }

      let feedback = `<h2>Result</h2>`;
      feedback += `<p><strong>MCQ Score:</strong> ${score} / ${total}</p>`;

      // Subjective Answers (basic validation and improvement suggestions)
      let sub1 = document.querySelector('textarea[name="sub1"]').value.trim();
      let sub2 = document.querySelector('textarea[name="sub2"]').value.trim();
      let sub3 = document.querySelector('textarea[name="sub3"]').value.trim();

      feedback += `<h3>Subjective Feedback</h3>`;

      feedback += `<p><b>Q8:</b> ${sub1.length > 50 ? 'Good explanation.' : 'Try to elaborate on why current ratio reflects liquidity.'}</p>`;
      feedback += `<p><b>Q9:</b> ${sub2.length > 50 ? 'Well discussed.' : 'Add points like historical cost, off-balance sheet items, etc.'}</p>`;
      feedback += `<p><b>Q10:</b> ${sub3.length > 50 ? 'Clear answer.' : 'Mention how both sides of the equation must always balance.'}</p>`;

      feedback += `<p><strong>Suggestion:</strong> Review concepts of liquidity analysis, accounting principles, and practical limitations of financial statements.</p>`;

      document.getElementById("result").innerHTML = feedback;
      document.getElementById("result").style.display = "block";
    }
  </script>

</body>
</html>
