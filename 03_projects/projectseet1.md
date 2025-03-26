#Projects related to DOM

## Project link
[Clock Here](https://stackblitz.com/edit/dom-project-chaiaurcode-ejx5njn7?file=index.html)


#Solution Code

##Project 1

```javascript

const buttons = document.querySelectorAll('.button');
const colors = ['grey', 'yellow', 'blue', 'yellow'];
buttons.forEach(function (button) {
  button.addEventListener('click', function (e) {
    document.body.style.backgroundColor = e.target.id;
  });
});

```

##Project 2

```javascript
const form = document.querySelector('form');
const calculate = form.querySelector('button');
form.addEventListener('submit', function (e) {
  e.preventDefault();
  const height = parseInt(document.querySelector('#height').value);
  const weight = parseInt(document.querySelector('#weight').value);
  const result = document.querySelector('#results');
  if (height === '' || height < 0 || isNaN(height)) {
    result.innerHTML = ' Please give a valid height';
  } else if (weight === '' || weight < 0 || isNaN(weight)) {
    result.innerHTML = ' Please give a valid weight';
  } else {
    const bmi = ((weight * 10000) / (height * height)).toFixed(2);
    result.innerHTML = `<span>${bmi}</span>`;
  }
});
```
##Project 3

```javascript
const clock = document.getElementById('clock');

setInterval(function () {
  let date = new Date().toLocaleTimeString();
  clock.innerHTML = `${date}`
}, 1000);

```
##Project 4

```javascript
let prev_guess = document.querySelector('.guesses');
let guess_remain = document.querySelector('.lastResult');
let LoworHigh = document.querySelector('.lowOrHi');
let guessremaining = 10;
const form = document.querySelector('form');
const random = Math.round(Math.random() * 99) + 1;

const arr = [];
console.log(random);
form.addEventListener('submit', function (e) {
  e.preventDefault();
  const guess = parseInt(document.querySelector('#guessField').value);
  prev_guess.innerHTML = `${guess}`;
  guess_remain.innerHTML = `${parseInt(guess_remain.innerHTML) - 1}`;
  guessremaining -= 1;
  if (guess < random) {
    LoworHigh.innerHTML = `Low`;
  } else if (guess > random) {
    LoworHigh.innerHTML = `High`;
  } else {
    LoworHigh.innerHTML = `Correct!`;
  }
  if (guessremaining < 0) {
    guess_remain.innerHTML = `0`;
    LoworHigh.innerHTML = `Lost! number was ${random}`;
    return;
  }
});


```

##Project 5

```javascript
const insert = document.querySelector('#insert');
const res = document.createElement('div');

window.addEventListener('keydown', function (e) {
  res.innerHTML = `
  <div class = 'color'>
  <table>
  <tr>
    <th>Key</th>
    <th>Key Code</th>
    <th>Code</th>
  </tr>
  <tr>
    <td>${e.key === " " ? "Space" : e.key}</td>
    <td>${e.keyCode}</td>
    <td>${e.code}</td>
  </tr>
</table>
</div>
  `;
  insert.appendChild(res);
});
```

##Project 6

```javascript
const changeColor = function (str) {
  let rand = Math.round(Math.random() * 16777215);
  document.body.style.backgroundColor = '#' + rand.toString(16);
};
let timer = 0;
document.querySelector('#start').addEventListener('click', function (e) {
  if (timer === 0) startTimer = setInterval(changeColor, 1000);
  timer = 1;
});

const stopTImer = document
  .querySelector('#stop')
  .addEventListener('click', function (e) {
    clearInterval(startTimer);
    timer = 0;
  });
```