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
Если нужно совершить несколько однотипных действий, то можно использовать цикл for. Вот его синтаксис:
```javascript
for (var num = 0; num <= 5; num++) {
  console.log(num);
}
// Выведет в «консоль» числа 0, 1, 2, 3, 4 и 5
```
Другой метод `querySelectorAll` возвращает все элементы, соответствующие селектору.

С помощью `for` удобно перебирать найденные элементы:
```javascript
var controls = document.querySelectorAll('.toggle-controls li');
for (var i = 0; i < controls.length; i++) {
  controls[i].innerHTML = 'переключатель';
}
// Во все элементы списка переключателей запишется строка «переключатель».
```
В этом фрагменте кода мы сделалем следующее:

1. Нашли элемент списка и у него вызвали метод `addEventListener`.
2. Указали отслеживать событие click или «щелчок мыши».
3. Для щелчков указали функцию-обработчик без названия, внутри которой вызвали функцию переключения фильтров.
```javascript
var toaster = document.querySelector('li.toaster');
toaster.addEventListener('click', function() {
  toggleFilter(toaster.dataset.filter);
});
```
Функция `clickControl` принимает найденный элемент и добавляет ему обработчик щелчков мыши, в котором вызывается функция переключения фильтра. Название фильтра для функции переключения берётся из data-атрибута самого элемента.
```javascript
function clickControl(control) {
  control.addEventListener('click', function() {
      toggleFilter(control.dataset.filter);
  });
};
```
Благодаря `clickControl` нам нужно добавить только одну строчку в цикл, чтобы все переключатели заработали:
```javascript
for (var i = 0; i < controls.length; i++) {
    ... 
    clickControl(controls[i]);
}
});
```
Чтобы изменить CSS-свойство элемента в скрипте, нужно обратиться к свойству style элемента. Например:
```javascript
var element = document.querySelector('.photo-original');
element.style.width = '10px';
```
Но названия свойств в JavaScript не всегда совпадают с их названиями в CSS. Например, CSS-свойство `left` совпадает с `style.left`, но CSS-свойство `baсkground-color` уже отличается: `style.backgroundColor`.

