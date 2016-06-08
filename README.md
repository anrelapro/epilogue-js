# epilogue-js
### filter using js


Найдём элемент списка с классом toaster и сохраним его в переменную control
```javascript
var control = document.querySelector('li.toaster');
```
Теперь к элементу списка, хранящемуся в переменной control, добавим класс active
```javascript
control.classList.add('active');
```
удалим у него класс active, добавленный ранее
```javascript
control.classList.remove('active');
```
Чтобы проверить, что в переменной есть элемент и с ним можно работать, используется условный оператор if
```javascript
var control1 = document.querySelector('li.toaster');
if (control1) {
    control1.classList.remove('active');
}
```
`querySelector` – это метод документа, который по указанному селектору ищет и возвращает первый найденный элемент, подходящий под селектор.

У элементов, которые мы находим с помощью `querySelector`, есть свойство `classList`, в котором хранится список классов элемента.

