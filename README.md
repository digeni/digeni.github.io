#digeni.github.io
function generateQuestion() {
  const num1 = Math.floor(Math.random() * 10);
  const num2 = Math.floor(Math.random() * 10);
  const operator = ['+', '-', '*', '/'][Math.floor(Math.random() * 4)];
  const question = `${num1} ${operator} ${num2}`;
  return question;
}

function checkAnswer(question, answer) {
  const correctAnswer = eval(question);
  return correctAnswer === parseInt(answer);
}

function playGame() {
  let score = 0;
  let question = generateQuestion();
  let answer = prompt(`What is ${question}?`);
  while (answer !== null) {
    if (checkAnswer(question, answer)) {
      score++;
      alert(`Correct! Your score is ${score}.`);
    } else {
      alert(`Incorrect. Your final score is ${score}.`);
      break;
    }
    question = generateQuestion();
    answer = prompt(`What is ${question}?`);
  }
}
