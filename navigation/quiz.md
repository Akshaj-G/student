---
layout: post 
title: CSA MCQ Lessons
search_exclude: true
permalink: /csa/quiz
type: lesson
---

<style>
  :root {
    --bg: #0f172a;
    --card: #1e293b;
    --border: #334155;
    --text: #e2e8f0;
    --muted: #94a3b8;
    --accent: #3b82f6;
    --correct: #22c55e;
    --incorrect: #ef4444;
  }
  #quiz-app * { box-sizing: border-box; }
  #quiz-app {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    color: var(--text);
    background: var(--bg);
    padding: 24px 16px 60px;
    border-radius: 12px;
  }
  #quiz-app .wrap { max-width: 680px; margin: 0 auto; }
  #quiz-app h1 { font-size: 1.5rem; margin-bottom: 4px; }
  #quiz-app p.desc { color: var(--muted); margin-top: 0; margin-bottom: 24px; }
  #quiz-app .progress {
    display: flex; justify-content: space-between; align-items: center;
    margin-bottom: 16px; font-size: 0.9rem; color: var(--muted);
  }
  #quiz-app .bar { background: var(--border); border-radius: 999px; height: 6px; overflow: hidden; margin-bottom: 20px; }
  #quiz-app .bar-fill { background: var(--accent); height: 100%; transition: width 0.2s ease; }
  #quiz-app .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
  }
  #quiz-app pre.prompt {
    white-space: pre-wrap;
    font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
    font-size: 0.95rem;
    background: #0b1220;
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 12px;
    margin: 0 0 16px;
  }
  #quiz-app .option {
    display: block;
    width: 100%;
    text-align: left;
    background: #0b1220;
    border: 1px solid var(--border);
    color: var(--text);
    border-radius: 8px;
    padding: 12px 14px;
    margin-bottom: 10px;
    cursor: pointer;
    font-size: 0.95rem;
    white-space: pre-wrap;
    font-family: inherit;
  }
  #quiz-app .option:hover { border-color: var(--accent); }
  #quiz-app .option.correct { border-color: var(--correct); background: rgba(34,197,94,0.12); }
  #quiz-app .option.incorrect { border-color: var(--incorrect); background: rgba(239,68,68,0.12); }
  #quiz-app .option:disabled { cursor: default; }
  #quiz-app .feedback { margin-top: 14px; padding: 14px; border-radius: 8px; background: #0b1220; border: 1px solid var(--border); }
  #quiz-app .feedback.correct { border-color: var(--correct); }
  #quiz-app .feedback.incorrect { border-color: var(--incorrect); }
  #quiz-app .feedback strong { display: block; margin-bottom: 6px; }
  #quiz-app .hint-btn, #quiz-app .next-btn, #quiz-app .restart-btn {
    background: var(--accent);
    color: white;
    border: none;
    border-radius: 8px;
    padding: 10px 18px;
    font-size: 0.9rem;
    cursor: pointer;
    margin-top: 12px;
  }
  #quiz-app .hint-btn { background: transparent; border: 1px solid var(--border); color: var(--muted); }
  #quiz-app .hint-text { color: var(--muted); font-style: italic; margin-top: 10px; font-size: 0.9rem; }
  #quiz-app .result { text-align: center; padding: 40px 20px; }
  #quiz-app .result .score { font-size: 3rem; font-weight: 700; margin: 10px 0; }
  #quiz-app .missed-list { text-align: left; margin-top: 24px; }
  #quiz-app .missed-list li { margin-bottom: 8px; color: var(--muted); }
</style>

<div id="quiz-app">
<div class="wrap">
  <h1>AP CSA Weak Spots Review</h1>
  <p class="desc">Targeted practice on the topics missed on Practice Exam 1 — constructors, casting, conditionals, loop equivalence, recursion, and 2D arrays.</p>
  <div class="progress">
    <span id="progress-text"></span>
    <span id="score-text"></span>
  </div>
  <div class="bar"><div class="bar-fill" id="bar-fill"></div></div>
  <div class="card" id="quiz-root"></div>
</div>
</div>

{% raw %}
<script>
const QUESTIONS = [
  {
    id: "q1",
    prompt: "What does this code print?\n\nint a = 7;\nint b = 2;\ndouble result = a / b;\nSystem.out.println(result);",
    options: [
      { id: "a", text: "3.5" },
      { id: "b", text: "3.0" },
      { id: "c", text: "4.0" },
      { id: "d", text: "Compile error" }
    ],
    correct: "b",
    hint: "Look at the types of a and b before the division happens, not after.",
    explanation: "a and b are both int, so a / b performs integer division FIRST (7/2 = 3, truncated), and only then is the int result 3 widened to the double 3.0 for assignment. Casting one operand to double before dividing is what you'd need for 3.5."
  },
  {
    id: "q2",
    prompt: "Which constructor correctly initializes a Painting class with instance variables 'title' (String) and 'year' (int)?",
    options: [
      { id: "a", text: "public Painting(String title, int year) { title = title; year = year; }" },
      { id: "b", text: "public Painting(String title, int year) { this.title = title; this.year = year; }" },
      { id: "c", text: "public void Painting(String title, int year) { this.title = title; this.year = year; }" },
      { id: "d", text: "public Painting() { this.title = title; this.year = year; }" }
    ],
    correct: "b",
    hint: "A constructor has no return type, and when a parameter shares a name with an instance variable, you need a way to tell them apart.",
    explanation: "Constructors never have a return type (so option C is wrong). When the parameter name matches the instance variable name, 'this.title = title' is required to assign the parameter's value to the instance variable; without 'this.', option A just assigns the parameter to itself and the fields stay uninitialized."
  },
  {
    id: "q3",
    prompt: "A program needs to print \"Pass\" if score >= 60, \"Honors\" if score >= 90, and \"Fail\" otherwise. Which code is correct?",
    options: [
      { id: "a", text: "if (score >= 60) System.out.println(\"Pass\");\nelse if (score >= 90) System.out.println(\"Honors\");\nelse System.out.println(\"Fail\");" },
      { id: "b", text: "if (score >= 90) System.out.println(\"Honors\");\nelse if (score >= 60) System.out.println(\"Pass\");\nelse System.out.println(\"Fail\");" },
      { id: "c", text: "if (score >= 60) System.out.println(\"Pass\");\nif (score >= 90) System.out.println(\"Honors\");\nSystem.out.println(\"Fail\");" },
      { id: "d", text: "if (score < 60) System.out.println(\"Fail\");\nif (score >= 60) System.out.println(\"Pass\");\nif (score >= 90) System.out.println(\"Honors\");" }
    ],
    correct: "b",
    hint: "In a chain of else-if checks, order matters — put the most restrictive condition first.",
    explanation: "Because score >= 60 is also true whenever score >= 90, checking >= 60 first (option A) would always print \"Pass\" and never reach the \"Honors\" branch for a 95. The most restrictive condition (>= 90) has to come first so it's checked before the looser one."
  },
  {
    id: "q4",
    prompt: "Which while loop is equivalent to this for loop?\n\nfor (int i = 0; i < 5; i++) {\n    System.out.println(i);\n}",
    options: [
      { id: "a", text: "int i = 0;\nwhile (i < 5) {\n    System.out.println(i);\n}" },
      { id: "b", text: "int i = 0;\nwhile (i < 5) {\n    System.out.println(i);\n    i++;\n}" },
      { id: "c", text: "int i = 0;\nwhile (i <= 5) {\n    i++;\n    System.out.println(i);\n}" },
      { id: "d", text: "int i = 1;\nwhile (i < 5) {\n    System.out.println(i);\n    i++;\n}" }
    ],
    correct: "b",
    hint: "A for loop has three parts: initialization, condition, update. All three need to show up in the while version, in the right places.",
    explanation: "The for loop's init (i=0) goes before the loop, the condition (i<5) becomes the while condition, and the update (i++) must be the LAST thing inside the loop body. Option A is missing the update entirely, so it would loop forever."
  },
  {
    id: "q5",
    prompt: "This loop is supposed to print the digits of n from left to right, but has a bug:\n\nint n = 1234;\nwhile (n > 0) {\n    System.out.print(n % 10);\n    n = n / 10;\n}\n\nWhat's actually happening?",
    options: [
      { id: "a", text: "It prints digits left to right correctly: 1234" },
      { id: "b", text: "It prints digits in reverse: 4321" },
      { id: "c", text: "It throws an ArithmeticException" },
      { id: "d", text: "It loops forever" }
    ],
    correct: "b",
    hint: "n % 10 always gives you the last digit of whatever n currently is.",
    explanation: "n % 10 extracts the ones digit each time (4, then 3, then 2, then 1 after n/10 strips it off), so the digits print in reverse order of how they appear in the number. Fixing this to print left-to-right requires a different approach, like finding the leftmost digit's place value first."
  },
  {
    id: "q6",
    prompt: "How many times does \"xx\" appear as a substring in \"xxxx\" (counting overlapping occurrences)?\n\nString s = \"xxxx\";\nint count = 0;\nint i = 0;\nwhile (i <= s.length() - 2) {\n    if (s.substring(i, i + 2).equals(\"xx\")) {\n        count++;\n    }\n    i++;\n}",
    options: [
      { id: "a", text: "2" },
      { id: "b", text: "3" },
      { id: "c", text: "4" },
      { id: "d", text: "1" }
    ],
    correct: "b",
    hint: "Since i increases by 1 each time (not 2), overlapping matches both get counted.",
    explanation: "Checking positions i=0,1,2 (since s.length()-2 = 2): substring(0,2)=\"xx\" ✓, substring(1,3)=\"xx\" ✓, substring(2,4)=\"xx\" ✓. All three overlapping windows match, giving count = 3."
  },
  {
    id: "q7",
    prompt: "What does this recursive method return for printNums(3)?\n\npublic static int printNums(int n) {\n    if (n <= 0) {\n        return 0;\n    }\n    return n + printNums(n - 1);\n}",
    options: [
      { id: "a", text: "3" },
      { id: "b", text: "6" },
      { id: "c", text: "9" },
      { id: "d", text: "0" }
    ],
    correct: "b",
    hint: "Write out the call stack: printNums(3) = 3 + printNums(2), and so on down to the base case.",
    explanation: "printNums(3) = 3 + printNums(2) = 3 + (2 + printNums(1)) = 3 + (2 + (1 + printNums(0))) = 3 + 2 + 1 + 0 = 6. This is the classic 'sum down to the base case' recursion pattern."
  },
  {
    id: "q8",
    prompt: "Which code correctly copies the values from a 2D array into a single ArrayList<Integer>?\n\nint[][] grid = {{1, 2}, {3, 4}};\nArrayList<Integer> list = new ArrayList<Integer>();",
    options: [
      { id: "a", text: "for (int i = 0; i < grid.length; i++) {\n    list.add(grid[i]);\n}" },
      { id: "b", text: "for (int i = 0; i < grid.length; i++) {\n    for (int j = 0; j < grid[i].length; j++) {\n        list.add(grid[i][j]);\n    }\n}" },
      { id: "c", text: "list.add(grid);" },
      { id: "d", text: "for (int[] row : grid) {\n    list.add(row);\n}" }
    ],
    correct: "b",
    hint: "grid[i] is a whole row (an int array), not a single number — you need to go one level deeper to get individual elements.",
    explanation: "grid[i] is an int[] (a row), which can't be added to an ArrayList<Integer> that expects single int values. You need nested loops: the outer loop picks a row (i), the inner loop picks a column (j), and grid[i][j] gives the individual element to add."
  },
  {
    id: "q9",
    prompt: "What does this method do, in plain English?\n\npublic static boolean mystery(int[] arr) {\n    for (int i = 1; i < arr.length; i++) {\n        if (arr[i] < arr[i - 1]) {\n            return false;\n        }\n    }\n    return true;\n}",
    options: [
      { id: "a", text: "Checks if the array is sorted in non-decreasing order" },
      { id: "b", text: "Checks if the array contains duplicate values" },
      { id: "c", text: "Returns the largest value in the array" },
      { id: "d", text: "Checks if the array is sorted in decreasing order" }
    ],
    correct: "a",
    hint: "It compares each element to the one before it — what would make that comparison fail?",
    explanation: "The method compares each element to the previous one; if it ever finds a value smaller than the one before it (arr[i] < arr[i-1]), the array isn't in non-decreasing order, so it returns false immediately. If it never finds that, the array is sorted ascending (or has equal adjacent values), so it returns true."
  },
  {
    id: "q10",
    prompt: "A survey of 50 students shows 30 prefer Course A and 20 prefer Course B. A report concludes \"Course A is twice as popular as Course B among all students at the school.\" What's the issue with this conclusion?",
    options: [
      { id: "a", text: "30 is not actually twice 20, so the math is wrong" },
      { id: "b", text: "The sample of 50 students may not represent the whole school, so the conclusion overgeneralizes" },
      { id: "c", text: "There is no issue; the conclusion is valid" },
      { id: "d", text: "The survey should have used percentages instead of counts" }
    ],
    correct: "b",
    hint: "Think about the gap between what the data actually shows and what the conclusion claims.",
    explanation: "The survey only sampled 50 students, but the conclusion claims something about 'all students at the school.' Without knowing the sample is representative of the full school population, extending a result from a subset to the whole group is an overgeneralization — a common AP CSA data-analysis pitfall separate from any arithmetic."
  }
];

let current = 0;
let score = 0;
let answered = false;
const missed = [];

const root = document.getElementById("quiz-root");
const progressText = document.getElementById("progress-text");
const scoreText = document.getElementById("score-text");
const barFill = document.getElementById("bar-fill");

function render() {
  if (current >= QUESTIONS.length) {
    renderResult();
    return;
  }

  const q = QUESTIONS[current];
  answered = false;

  progressText.textContent = `Question ${current + 1} of ${QUESTIONS.length}`;
  scoreText.textContent = `Score: ${score}/${current}`;
  barFill.style.width = `${(current / QUESTIONS.length) * 100}%`;

  root.innerHTML = `
    <pre class="prompt">${escapeHtml(q.prompt)}</pre>
    <div id="options"></div>
    <button class="hint-btn" id="hint-btn">Show hint</button>
    <div id="hint-area"></div>
    <div id="feedback-area"></div>
  `;

  const optionsDiv = document.getElementById("options");
  q.options.forEach(opt => {
    const btn = document.createElement("button");
    btn.className = "option";
    btn.textContent = `${opt.id.toUpperCase()}. ${opt.text}`;
    btn.addEventListener("click", () => selectAnswer(opt.id));
    optionsDiv.appendChild(btn);
  });

  document.getElementById("hint-btn").addEventListener("click", () => {
    document.getElementById("hint-area").innerHTML = `<div class="hint-text">${escapeHtml(q.hint)}</div>`;
  });
}

function selectAnswer(choiceId) {
  if (answered) return;
  answered = true;

  const q = QUESTIONS[current];
  const isCorrect = choiceId === q.correct;
  if (isCorrect) {
    score++;
  } else {
    missed.push(q);
  }

  const buttons = document.querySelectorAll(".option");
  buttons.forEach((btn, i) => {
    const opt = q.options[i];
    btn.disabled = true;
    if (opt.id === q.correct) btn.classList.add("correct");
    else if (opt.id === choiceId) btn.classList.add("incorrect");
  });

  const feedbackArea = document.getElementById("feedback-area");
  feedbackArea.innerHTML = `
    <div class="feedback ${isCorrect ? "correct" : "incorrect"}">
      <strong>${isCorrect ? "Correct." : "Not quite."}</strong>
      ${escapeHtml(q.explanation)}
    </div>
    <button class="next-btn" id="next-btn">${current + 1 < QUESTIONS.length ? "Next question" : "See results"}</button>
  `;

  document.getElementById("next-btn").addEventListener("click", () => {
    current++;
    render();
  });
}

function renderResult() {
  progressText.textContent = "Done";
  scoreText.textContent = `Score: ${score}/${QUESTIONS.length}`;
  barFill.style.width = "100%";

  let missedHtml = "";
  if (missed.length > 0) {
    missedHtml = `
      <div class="missed-list">
        <strong>Review these again:</strong>
        <ul>
          ${missed.map(q => `<li>${escapeHtml(q.prompt.split("\n")[0])}</li>`).join("")}
        </ul>
      </div>
    `;
  }

  root.innerHTML = `
    <div class="result">
      <div>You scored</div>
      <div class="score">${score}/${QUESTIONS.length}</div>
      ${missedHtml}
      <button class="restart-btn" id="restart-btn">Restart quiz</button>
    </div>
  `;

  document.getElementById("restart-btn").addEventListener("click", () => {
    current = 0;
    score = 0;
    missed.length = 0;
    render();
  });
}

function escapeHtml(str) {
  const div = document.createElement("div");
  div.textContent = str;
  return div.innerHTML;
}

render();
</script>
{% endraw %}