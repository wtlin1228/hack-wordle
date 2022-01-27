Want to enjoy your vacation? Do your children keep asking you to play wordle with them? Follow those easy steps to build a wordle clone that can be play without waiting until next day 🍻

1. change this line

```js
// original is e.solution=Da(e.today)
e.solution=Da(Number(localStorage.getItem('hack-wordle-solution')) || e.today)
```

2. add those to body of html

```html
<input id="date" type="date" min="2022-01-01">

<script>
  var selectElement = document.querySelector('#date');

  var previousDate = localStorage.getItem('hack-wordle-solution');
  if (previousDate) {
    selectElement.value = new Date(Number(previousDate)).toISOString().split('T')[0];
  }

  selectElement.addEventListener('change', (event) => {
    localStorage.removeItem('gameState');
    
    const targetDate = new Date(event.target.value).getTime();
    localStorage.setItem('hack-wordle-solution', targetDate);
    
    location.reload();
  });
</script>
```

3. Serve it on GitHub page. Send it to your children. And enjoy your vocation 🍺
