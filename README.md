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
