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