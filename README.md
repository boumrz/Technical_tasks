Промсвязьбанк - https://qr.nspk.ru/proxyapp/logo/bank100000000010.png
ПАО СКБ - банк - https://qr.nspk.ru/proxyapp/logo/bank100000000003.png
АО ГАЗЭНЕРГОБАНК - https://qr.nspk.ru/proxyapp/logo/bank100000000043.png
ПАО АКБ АВАНГАРД - https://qr.nspk.ru/proxyapp/logo/bank100000000028.png
ООО ПНКО ЭЛПЛАТ - https://qr.nspk.ru/proxyapp/logo/bank100000000086.png

# Technical tasks

## 1. Реализовать работу банкомата
Необходимо написать функцию банкомата, которая бы возвращала массив возможных номиналов денег по запросу пользователя.

Номиналы должны выдаваться максимально крупные с минимально возможным общим количеством выданных купюр. В случае, если нет возможности по каким-то причинам выдать пользователю деньги, необходимо вывести ошибку через стандартный механизм ошибок.

Результат возвращается в формате от большего к меньшему — ['5000x1', '1000x3', ...]. Дополнительный уровень — вводятся ограничение на количество купюр в банкомате.

```js
// 1 level
const nominals = [10, 50, 100, 500, 1000, 5000];
 
/**
 * ATM
 *
 * @param {number} amount
 * @param {number[]} nominals
 * @returns {string[]} Returns format ['Nx3', 'Nx4', 'Nx1']
 */
function atm(amount, nominals) {
    // ...
}
 
// 2 level
const nominals = [10, 50, 100, 500, 1000, 5000];
const limits = [10, 5, 4, 3, 2, 1];
 
/**
 * ATM
 *
 * @param {number} amount
 * @param {number[]} nominals
 * @param {number[]} limits
 * @returns {string[]} format ['Nx3', 'Nx4', 'Nx1']
 */
function atm(amount, nominals, limits) {
    // ...
}
```

## 2. Написать функцию intersect
Написать функцию, которая находит пересечение массивов, то есть те элементы, которы встречаются и в первом массиве и во втором. Представить решение задачи с использованием HashMap и без него, оценить сложность алгоритма для этих решений.

```js
const a = [1, 10, 2, 6, 9, -32];
const b = [-7, 1, 9, 8, 0, 1, 10];
 
intersect(a, b); // [1, 9, 10]
 
/**
 * Intersect
 * @param {number[]} a
 * @param {number[]} b
 * @returns {number[]}
 */
function intersect(a, b) {
    // ...
}
```

## 3. Отсортирован ли массив целых чисел в порядке возрастания?
Написать функцию, которая проверяет, отсортирован ли массив целых чисел в порядке возрастания?

```js
const a = [1, 10, 2, 6, 9, -32];
const b = [1, 2, 3, 4, 10, 11, 20];
 
  
inAscOrder(a); // false
inAscOrder(b); // true
 
/**
 * Are the numbers in order?
 *
 * @param {number[]} input The input data
 * @returns {boolean} Returns status
 */
function inAscOrder(input) {
    // ...
}
```

## 4. Сортировки
Реализовать любую сортировку

 ## 5. Структуры данных 
 Реализовать любую структуру данных (хэш-таблицу, двусвязный список, стек и тд)
 * Пример двусвязного списка на js:
 ```js
 function Node(data) {
    this.data = data;
    this.previous = null;
    this.next = null;
}
 
class DoublyLinkedList {
    constructor() {
        this.head = null;
        this.tail = null;
        this.count = 0;
    }
     
    add(data) {
        const node = new Node(data);
        this.count++;
 
        if (!this.head) {
            this.head = node;
            this.tail = node;
            return;
        }
 
        node.previous = this.tail;
        this.tail.next = node;
        this.tail = node;
    }
 
    traverse(fn) {
        let current = this.head;
 
        while (current) {
            if (fn) {
                fn(current);
            }
             
            current = current.next;
        }
    }
 
    length() {
        return this.count;
    }
}
 ```

 ## 6. Функцию, которая определяет количество символов в строке
Написать функцию, которая считает количество символов и выводит результат в массиве в следующем формате:
```js
    const a = 'EEFDSFEERTGHJJH';
    
    /**
    * counterString
    * @param {string[]} str
    * @returns {number[]}
    */
    function counterString(str) {
        // ...
    }

    counterString(a); // ['Ex4', Fx2, Dx1, Sx1, Rx1, Tx1, Gx1, Hx2, Jx2]
```