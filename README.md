1. change this line

```js
// original is e.solution=Da(e.today)
e.solution=Da(Number(localStorage.getItem('hack-wordle-solution')) || e.today)
```

2. add those to body of html

```html
<input id="date" type="date">

<script>
  const selectElement = document.querySelector('#date');

  const previousDate = localStorage.getItem('hack-wordle-solution');
  selectElement.value = new Date(Number(previousDate)).toISOString().split('T')[0];

  selectElement.addEventListener('change', (event) => {
    localStorage.removeItem('gameState');
    
    console.log(event.target.value);
    const targetDate = new Date(event.target.value).getTime();
    localStorage.setItem('hack-wordle-solution', targetDate);
    
    location.reload();
  });
</script>
```

3. send it to your children and enjoy your vocation