# Переписал ф-цию сортировки на более оптимальный вариант
```
// Новый
function quickSort(fruits, left, right) {
	var index;
	if (parseInt(fruits.length) > 1) {
	left = typeof left != "number" ? 0 : left;
	right = typeof right != "number" ? fruits.length - 1 : right;
	index = partition(fruits, left, right);
	if (left < index - 1) {
		quickSort(fruits, left, index - 1);
	}
	if (index < right) {
		quickSort(fruits, index, right);
	}
	}
	return fruits;
};
```
# Исправил работу кнопки меньше
```
document.getElementById('btnLess').addEventListener('click', function () {
if (gameRun) {
	if (minValue === maxValue || minValue === answerNumber) {
		const phraseRandom = Math.round(Math.random() * 2);
		const answerPhrase = (phraseRandom === 1) ?
			`Вы загадали неправильное число!\n\u{1F914}` :
			`Я сдаюсь..\n\u{1F92F}`;
		answerField.innerText = answerPhrase;
		gameRun = false;
	} else {
		maxValue = answerNumber - 1;
		answerNumber = Math.floor((minValue + maxValue) / 2);
		orderNumber++;
		orderNumberField.innerText = orderNumber;
		const phraseRandom = Math.round(Math.random() * 2);
		const answerPhrase = (phraseRandom === 0) ? `Вы загадали число ${answerNumber}?` :
			(phraseRandom === 1) ? `Да это легко! Ты загадал ${answerNumber}!` :
				`Наверное, это число ${answerNumber}.`;
		answerField.innerText = answerPhrase;
	}
}
})
```