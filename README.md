## DAY 1

1.a. Write a function which count the number of occurrence of words in a paragraph or a sentence.The function `countWords` takes a paragraph and two words as parameters. It compare  which word is most frequently occurred in the paragraph.
```js
const paragraph = 'I love teaching. If you do not love teaching what else can you love. I love JavaScript if you do not love something which can give life to your application what else can you love.';
console.log(countWords(paragraph,'love', 'you'));
The word love more frequently occurred than you.
const paragraph = 'I love teaching. If you do not love teaching what else can you love. I love Javascript if you do not love something which can give life to your appication what else can you love.';
function countWords(paragraph){
paragraph = paragraph.replace(/(^\s*)|(\s*$)/gi, "");
paragraph = paragraph.replace(/[ ]{2,}/gi, " ");
paragraph = paragraph.replace(/\n /, "\n");
return paragraph.split(' ').length;
function countWords(paragraph, word1, word2){

}
console.log(countWords(paragraph, 'love', 'you'));
```
1.b. Write a function called ***cleanText***. The function takes raw text as a parameter and returns the clean text.
```js
const sentence = `%I $am@% a %tea@cher%, &and& I lo%#ve %tea@ching%;. There $is nothing; &as& mo@re rewarding as educa@ting &and& @emp%o@wering peo@ple. ;I found tea@ching m%o@re interesting tha@n any other %jo@bs. %Do@es thi%s mo@tivate yo@u to be a tea@cher!?`;
    console.log(cleanText(sentence));
     const sentence = `%I $am@% a %tea@cher%, &and& I lo%#ve %tea@ching%;. There $is nothing; &as& mo@re rewarding as educa@ting &and& @emp%o@wering peo@ple. ;I found tea@ching m%o@re interesting tha@n any other %jo@bs. %Do@es thi%s mo@tivate yo@u to be a tea@cher!?`;
      const cleanText = rawText => rawText.replace(/[,;#%&@!$']/g, '');
      console.log(cleanText(sentence));
`I am a teacher and I love teaching. There is nothing as more rewarding as educating and empowering people. I found teaching more interesting than any other jobs. Does this motivate you to be a teacher?`
```  

1.c. After cleaning the text in the sentence from question number b you will get the following text. Count the number of words in this text. Don't include words with only one letter.

```js
const sentence =  `I am a teacher and I love teaching. There is nothing as more rewarding as educating and empowering people. I found teaching more interesting than any other jobs. Does this motivate you to be a teacher?`
console.log(countWords(sentence));

31
   const cleanedText = `I am a teacher and I love teaching. There is nothing as more rewarding as educating and empowering people. I found teaching more interesting than any other jobs. Does this motivate you to be a teacher?`;
      const countWords = text => {
        let count = 0;
        const words = text.replace(/[,;#%&@!$'.?]/g, '').split(' ');
        for (const word of words) {
          if (word.length > 1) count++;
        }

        return count;
      };
      console.log(countWords(sentence));
```
1.d. How many words were used to construct this sentence. Now, don't exclude one letter words.
```js
console.log(varietyOfWords(sentence))
28
```

2.a. Looping a triangle: Write a loop that makes seven calls to console.log to output the following triangle:
```js
#
##
###
####
#####
######
#######
```
> It may be useful to know that you can find the length of a string by writing .length after it.

var content = '';

for (var i = 0; i < 7; i++) {
    content = content + '#';
    console.log(content);
}

2.b. Write a function which returns array of seven random numbers in a range of 0-9. All the numbers must be unique
```js
sevenRandomNumbers()
[1,4,5,7,9,8,0]

var arr = [];
while(arr.length < 8){
    var r = Math.floor(Math.random() * 10) + 1;
    if(arr.indexOf(r) === -1) arr.push(r);
}
console.log(arr);

```
2c. Reversing an array: Arrays have a reverse method which changes the array by inverting the order in which its elements appear. For this exercise, write a function, reverseArray. The  reverseArray, takes an array as argument and produces a new array that has the same elements in the inverse order. Without reverse method.
```js
console.log(reverseArray(["A", "B", "C"]));
["C", "B", "A"]
```
function reverseArray(array) {
  result = [];
  for (let item of array) {
    result.unshift(item);
  }
  return result;
}

function reverseArrayInPlace(array) {
  let len = array.length;
  for (let i = 0; i < Math.floor(len/2); i++) {
    console.log(i, len-i-1, array[i], array[len-i-1], array);
    let swap = array[i];
    array[i] = array[len-i-1];
    array[len-i-1] = swap;
  }
  return array;
}

console.log(reverseArray(["A", "B", "C"]));
// → ["C", "B", "A"];

2.d. Write a function which check if items of an array are unique?
```js
const arrOne = [1, 4, 6, 2, 1];
console.log(checkUniqueness(arrOne));
false
const arrTwo = [1, 4, 6, 2, 3]
console.log(checkUniqueness(arrTwo));
true
```
function areUnique(arr)
{
    let n = arr.length;
 
    // Put all array elements in a map
    let s = new Set();
    for (let i = 0; i < n; i++) {
        s.add(arr[i]);
    }
 
    // If all elements are unique, size of
    // set should be same array.
    return (s.size == arr.length);
}
 
    let arr = [ ];
 
    if (areUnique(arr)) {
        document.write("True");
    }
    else {
        document.write("False");
