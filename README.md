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

воспользуемся операцией «склеивания» строк
```javascript
'li.' + filterName // результат: 'li.toaster'
```
функция переключения фильтра
```javascript
function toggleFilter(filterName) {
    var control = document.querySelector('li.' + filterName);
    if (control) {
        control.classList.add('active');
    }

    var photo = document.querySelector('.photo');
    if (photo) {
        photo.classList.add(filterName);
    }
}
```
Чтобы с помощью JavaScript считать значение data-атрибутов, нужно использовать свойство `dataset`. Пример:
```html
<div class="control" data-filtername="walden"></div>
```
```javascript
var control = document.querySelector('.control');
var filter = control.dataset.filtername;
// в переменной filter теперь строка «walden»
```
Добавлять содержимое в HTML-элемент через JavaScript можно с помощью свойства innerHTML:
```javascript
var control = document.querySelector('.control');
control.innerHTML = 'walden';
```


