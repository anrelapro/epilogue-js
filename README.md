# epilogue-js
### filter using js


1. Найдём элемент списка с классом toaster и сохраним его в переменную control
```javascript
var control = document.querySelector('li.toaster');
```
2. Теперь к элементу списка, хранящемуся в переменной control, добавим класс active
```javascript
control.classList.add('active');
```
3. удалим у него класс active, добавленный ранее
```javascript
control.classList.remove('active');
```
