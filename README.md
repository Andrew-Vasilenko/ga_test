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


# Задача №4:
Имеется ниже представленная таблица. В ней 5 авторов и 5 книг. Что вернет каждый из запросов?

<pre><code>
USERS                                             BOOKS
| userId | name    |                              | bookId | title  | userId |
______________________________________________________________________________
|    1   | Иван    |                              |    1   | Книга1 |   1    |
|    2   | Игнат   |                              |    2   | Книга2 |   1    |
|    3   | Игорь   |                              |    3   | Книга3 |   2    |
|    4   | Ибрагим |                              |    4   | Книга4 |   2    |
|    5   | Илья    |                              |    5   | Книга5 |   3    |
</code></pre>
 
### А. 
`SELECT u.name, b.title FROM 
users as u
LEFT JOIN books as b
ON u.userId = b.userId
`	
### Ответ (A): 
<pre><code>
| name | title   |                              
__________________________
|    Иван    | Книга1 |                              
|    Иван    | Книга2 |                              
|    Игнат   | Книга3 |                              
|    Игнат   | Книга4 |                              
|    Игорь   | Книга5 |                              
|    Ибрагим | null   |                              
|    Илья    | null   |                             
</code></pre>

### Б.
`SELECT u.name, b.title FROM 
users as u
INNER JOIN books as b
ON u.userId = b.userId
`
### Ответ (Б): 
<pre><code>
| name | title   |                              
__________________________
|    Иван    | Книга1 |                              
|    Иван    | Книга2 |                              
|    Игнат   | Книга3 |                              
|    Игнат   | Книга4 |                              
|    Игорь   | Книга5 |    
</code></pre>

