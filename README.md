# Задача №1:
Написать, в каком порядке будет вызвана консоль

<pre><code>
console.log(1)
Promise
    .resolve()
    .then(() => console.log(2))
    .then(() => {
        setTimeout(() => {
            console.log(3)
        }, 0)
    })
    .then(() => console.log(4));
</code></pre>

### Ответ: 1,2,4,3
### Пояснение: 
setTimeout(0) ставит функцию console.log() в конец очереди событий


