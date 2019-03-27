//JS QUIZ PRACTICE
```JS
var qAndA = [
    ['How many stars are on the American flag?', 50],
    ['What day in July is Independence Day?', 4],
    ['How many legs does a spider have?', 8],
];
var correct = [];
var wrong = [];
var correctAnswers = 0;
var question;
var answer;
var response;
var html;

console.log("checkpoint A");
function print(message) {
  console.log("in print()");
  var outputDiv = document.getElementById('output');
  outputDiv.innerHTML = message;
}
console.log("checkpoint B");
function buildList(arr){
  console.log("in buildList()");
  var listItem = '<ol>';
  for (var i = 0; i < arr.length; i += 1){
    listItem += '<li>' + arr[i] + '</li>';
  }
  listItem += '</ol>';
  return listItem;
}

console.log("checkpoint C");
for (var i = 0; i < qAndA.length; i += 1 ){
  console.log("in for loop");
  console.log("for loop i:");
  console.log(i);
  question = qAndA[i][0];
  answer = qAndA[i][1];
  response = parseInt(prompt(question));
  if (response === answer){
    correctAnswers += 1;
    correct.push(question);
  }else{
    wrong.push(question);
  }
}

console.log("checkpoint D");
html = "You got " + correctAnswers + " questions correct!";
html += '<h2>You got these questions correct:</h2>';
html += buildList(correct);
html += '<h2>You got these questions wrong:</h2>';
html += buildList(wrong);
print(html);
```