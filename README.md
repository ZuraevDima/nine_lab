___
# МИНИСТЕРСТВО НАУКИ И ВЫСШЕГО ОБРАЗОВАНИЯ РОССИЙСКОЙ ФЕДЕРАЦИИ ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ БЮДЖЕТНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ПРОФЕСИОНАЛЬНОГО ОБРАЗОВАНИЯ «САХАЛИНСКИЙ ГОСУДАРСТВЕННЫЙ УНИВЕРСИТЕТ»
### <p align="center">Лабораторная работа №9 «JavaScript».</p> 
#### <br><p align="right">Подготовил студент направления подготовки 01.03.02 «Прикладная математика и информатика»<br> Института естественных наук и техносферной безопасности<br> Зураев Дмитрий Бакенович.</p><br><p align="right">Научный руководитель:<br> Соболев Евгений Игоревич</p><br> <p align="center">Южно-Сахалинск 2023 г.</p>
___
### <p align="center">Введение</p>
<p align="justify"> <b>JavaScript</b> является одним из самых популярных языков программирования, применяемых веб-разработкой. Он обладает мощными возможностями для работы с функциями, что делает его незаменимым инструментом для создания интерактивных и динамических веб-приложений.
</p>

### <p align="center">Цели</p>
<p align="justify">Ознакомиться с основными концепциями и возможностями JavaScript в области работы с функциями. Функции в JavaScript являются одним из ключевых строительных блоков языка, позволяющих организовывать код в модули и повторно использовать его.</p>

### <p align="center">Задачи</p>
<p align="justify">Применить технологию JS.</p>

____________________
## <p align="center">_Решение_</p>

1. Есть некоторая строка (`var str = 'fgfggg';`), что будет, если мы возьмем `str[0]`?
```javascript
function one(){ 
            var str = 'fgfggg';
            console.log("будет выведен первый символ строки " + str[0]);
        }
```
2. Дана функция, она принимает в качестве аргументов строки `'*'`, `'1'`, `'b'`, `'1c'`, реализуйте ее так, что бы она вернула строку '`1*b*1c`'
```javascript
function builder(sign, str1, str2, str3){
            return `${str1}${sign}${str2}${sign}${str3}`;
        }
        function testTwo(){
            console.log(builder('*', '1', 'b', '1c'));
        }
```
3. Дано дерево, надо найти сумму всех вершин
```javascript
 function three(){
            class TreeNode {
                constructor(value, left = null, right = null) {
                    this.value = value;
                    this.left = left;
                    this.right = right;
                }
            }
    
            function findSumOfNodes(root) {
                if (root === null) {
                    return 0;
                }
                let sum = root.value;
                sum += findSumOfNodes(root.left);
                sum += findSumOfNodes(root.right);
                return sum;
            }
            // Пример 
            //       1
            //      / \
            //     2   3
            //    / \
            //   4   5
            const tree = new TreeNode(1);
            tree.left = new TreeNode(2);
            tree.right = new TreeNode(3);
            tree.left.left = new TreeNode(4);
            tree.left.right = new TreeNode(5);

            const sum = findSumOfNodes(tree);
            console.log('Сумма вершин дерева:', sum); //15
        }
```
4. Нарисовать стилями полукруг.
```css
.four{
    border: 2px solid black;
    width: 200px;
    margin-top: 20px;
    margin-bottom: 20px;
}
.circle{
    width: 150px;
    height: 150px;
    border-right: 2px solid #f00;
    border-radius: 0 50% 50% 0; 
}
```
```html
<div class="four">
        <p><b>Задание 4:</b></p>
        <p class="circle"></p>
</div>
```
5. Есть массив в котором лежат объекты с датами, отсортировать по датам.
```javascript
function five(){
            var dates = [new Date('2022-01-01'), new Date('2018-6-1'), new Date('2023-10-26'), new Date('2028-7-5')];
            for(let i=0; i < dates.length-1; i++){
                for (let j=0; j < dates.length-1-i; j++)
                {
                    if (dates[j]<=dates[j+1]){
                        let temp = dates[j];
                        dates[j]=dates[j+1];
                        dates[j+1] = temp;
                    }
                }
            }
            for (let i=0; i<dates.length; i++)
                console.log(dates[i].toString());
        }
```
6. Есть несколько слов, определить состоят ли они из одних и тех же букв(`'кот'`, `'ток'`, `'окт'`)
```javascript 
function six(){
            function areAnagrams(words) {
                const sortedWords = words.map(word => word.split('').sort().join(''));
                const firstWord = sortedWords[0];
                for (let i = 1; i < sortedWords.length; i++) {
                    if (sortedWords[i] !== firstWord) {
                    return false;
                    }
                }
                return true;
            }
            const words = ['кот', 'ток', 'окт'];
            const result = areAnagrams(words);
            console.log('Слова являются анаграммами:', result);
        }
```
7. От них же. Числа от 1 до 100 лежат в массиве, они хаотично перемешанные, от туда изъяли одно число, надо найти, что это за число. алгоритм не должен превышать O(n^2) сложности.
```javascript 
function seven(){
            function findMissingNumber(arr)
            {
                let oneToHundredSum = 0;
                let totalSum = 0;
                for(let i = 1; i <= 100; i++) 
                    oneToHundredSum += i;
                for(let i = 0; i < arr.length; i++) 
                    totalSum += arr[i];
                return oneToHundredSum - totalSum;
            }
            // числа 8 нет в массиве
            let arr = [1, 2, 3, 4, 5, 6, 7, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100];
            let missingNumber = findMissingNumber(arr);
            console.log("Изъятое число: " + missingNumber);
        }
```
8. Реализовать сортировку пузырьком
```javascript
function eight(){
            var array = [1,2,3,7,5,1];
            for(let j=0; j < array.length-1; j++){
                for (let i=0; i < array.length-1; i++)
                {
                    if (array[i] <= array[i+1])
                    {
                        let temp = array[i];
                        array[i]=array[i+1];
                        array[i+1] = temp;
                    }
                }
            }
            for (let i=0; i < array.length; i++)
                console.log(array[i].toString());
        }
```
9. Обратная польская нотация
```javascript
function nine(){        
            function evaluateRPN(expression) {
                let stack = [];
    
                for (let i = 0; i < expression.length; i++) {
                    let element = expression[i];
                    if (!isNaN(parseFloat(element))) { // Если элемент - число
                        stack.push(parseFloat(element));
                    } else { // Если элемент - оператор
                        performOperation(element);
                    }
                }
                    // Возвращаем результат
                    return stack.pop();
                }
                function performOperation(operator) {
                    let operand2 = stack.pop();
                    let operand1 = stack.pop();
                    switch (operator) {
                    case '+':
                        stack.push(operand1 + operand2);
                        break;
                    case '-':
                        stack.push(operand1 - operand2);
                        break;
                    case '/':
                        stack.push(operand1 / operand2);
                        break;
                    case '*':
                        stack.push(operand1 * operand2);
                        break;
                    }
                }
    
                // входные данные
                // 8 9 + 1 7 - *
                // выходные данные
                // -102
                // 1. Сложение: 8 + 9 = 17
                // 2. Вычитание: 1 - 7 = -6
                // 3. Умножение: 17 * -6 = -102

                let expression = ['8', '9', '+', '1', '7', '-', '*'];
                let result = evaluateRPN(expression);
                console.log(result); 
        }
```
10. Реализовать функцию является ли слово палендром.
```javascript
function ten(){
            function Palindrom(str)
            {
                str = str.replaceAll(" ","");
                str = str.toLowerCase();    
                for(let i = 0; i < Math.floor(str.length / 2); i++)
                {
                    if(str[i] != str[str.length - (i+1)])
                    return `No, the word isn\`t a palindrome`;
                }
                return `Yes, the word is a palindrome`;;
            }//арозаупаланалапуазора "Утро Чорту"
            alert(Palindrom("Утро Чорту"));
        }
```

## <p align="center">_Вывод_</p>
В ходе выполнения данной лабораторной работы я ознакомился с функциями в JavaScript. Я изучил, как объявлять функции, передавать аргументы и возвращать значения.