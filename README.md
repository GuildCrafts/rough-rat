# Rough-Rat
## Description

Complete the basic algorithm scripting section here:
https://www.freecodecamp.com/map
## Specifications

Listed in the link above
### Required

_Do not remove these specs - they are required for all goals_.
- [x] The artifact produced is properly licensed, preferably with the [MIT license][mit-license].
## Quality Rubric

_What are some appropriate quality objectives for this goal? These are statements about the internal characteristics of the product that demonstrate fine design and craftspersonship, not its external features._
- Quality rubric one: Code is readable
- Quality rubric two: Complete all of Basic Algorithm Scripting
- Quality rubric three: comment on algorithms to explain steps. 
Zeze: https://www.freecodecamp.com/zezemanolo
Alicia: 


Basic Algorithm Scriptiong:
var zzs = "yolo";
//LG Week 1 Rough-Rat 
//Alicia and Zeze (Jose)

//Exercise 1
//===========================================================================
//Reverse a string:

function reverseString(str) {
 /* original thoughts:  var splitString = str.split();
  var reverseString = splitString.reverse();
  var joinArray = reverseString.join();*/

  return str.split("").reverse().join("");
}

reverseString("hello");
/* returns "olleh". learned I can chain methods! Also, strings are immutable in js so split string into array, reverse, then join the array to return results in string
*/

//Exercise 2
//===========================================================================

// Factorialize a number

function factorialize(num) {
  if ( num === 0){
  return 1;
  }
  return num * factorialize(num -1);
}
//if loop used to iterate thru every integer >0

factorialize(5);
//r declare function using # that will be factorialized as parameter 

//Exercise 3
// =========================================================================

//  Check for Palindromes
function palindrome(str) {
 //var rmZz = ;
 var alphaNum = str.toLowerCase().replace(/[\W_]/g, '');
 var reverseStr = alphaNum.split('').reverse().join('');
 return reverseStr === alphaNum;
}
// make all letters lower case and remove non alphanumeric characters 
// split string to array, reverse, join string 
palindrome("eye");

// Exercise 4
//==========================================================================
//find the longest word in a string

function findLongestWord(str) {
  var splitString = str.split(' ');
  var maxLength = 0;
  
  for (var i = 0; i < splitString.length; i++){
    if (splitString[i].length > maxLength){
      maxLength = splitString[i].length;
    }
  }
  return maxLength;
}

findLongestWord("The quick brown fox jumped over the lazy dog");

//Exercise 5
//===========================================================================

// Title case each word in the sentence
function titleCase(str) {
  return str.toLowerCase().split(' ').map(function(word) { 
     return (word.charAt(0).toUpperCase() + word.slice(1));
  
  }).join(' ');
}

titleCase("I'm a little tea pot");

//Exercise 6
//==========================================================================

//Get largest numbers from multiple arrays and store in in a separate array:
function largestOfFour(arr) {
    var newArrayz = [];
    for (var i = 0; i < arr.length; i++) {
        var largeNum = 0;
        for (var n = 0; n < arr[i].length; n++) {
            if (arr[i][n] > largeNum) {
                largeNum = arr[i][n];
            }
        }
        newArrayz[i] = largeNum;
    }
    return newArrayz;
    // You can do this!

}

largestOfFour([
    [4, 5, 1, 3],
    [13, 27, 18, 26],
    [32, 35, 37, 39],
    [1000, 1001, 857, 1]
]);

/*
1)Create a variable to store the results as an array.
2)Create an outer loop to iterate through the outer array.
3)Create a second variable to hold the largest number. This `  must be outside an inner loop so it won't be reassigned until `  we find a larger number.
4)Create said inner loop to work with the sub-arrays.
5)Check if the element of the sub array is larger than
  the currently stored largest number. If so, then update the number in the variable.
6)After the inner loop, save the largest number in the corresponding position inside of the results array.
7)And finally return said array*/

//Exercise 6
//============================================================================

//confirm the Ending.. check if string on left contains string on right function(left, right)
function confirmEnding(str, target) {
  return target === str.substr(str.length - target.length);// "Never give up and good luck will find you."
  // -- Falcor
  // this came with original code "return str;"
}

confirmEnding("Bastian", "n");

//Exercise 7
//============================================================================
//repeat a string, (# of times)

function repeatStringNumTimes(str, num) {
  // repeat after me
  if (num > 0){
  return str.repeat(num);
    //originally did "return str * num; but discovered replace method and atttempted "str.repeat(num);
  }
  return "";
 
}

repeatStringNumTimes("abc", 3);

//Exercise 8
//============================================================================
//Truncate a string
//truncate first string, if longer than 2nd then truncate and insert ... at End
function truncateString(str, num) {
  //var trunkZ = '';
  if (str.length > num && num > 3) {
    return str.slice(0, (num-3)) + '...';
    //return trunkZ;
  }
  else if (str.length > num && num <=3) {
    return str.slice(0, num) + '...';
  }
  else {
 return str;
  }
  // Clear out that junk in your trunk
  
  
}

truncateString("A-tisket a-tasket A green and yellow basket", 11);




//CHUNKY MONKEY
//V1.0
/*function chunkArrayInGroups(arr, size) {
build function splits arr by # on 2nd arguments
*/

function chunkArrayInGroups(arr, size) {
 var zzArray = [];
 var zzCount = 0;

  while(zzCount < arr.length){
   zzArray.push(arr.slice(zzCount, zzCount + size));
   zzCount += size;
  }
  // Break it up.
  return zzArray;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);

//Slasher Flick
//v1.0
/*
return remaining elements after chopping 2nd arg (#) from head of array

slasher([1, 2, 3], 2);
*/
function slasher(arr, howMany) {
  return arr.splice(howMany);
}

slasher([1, 2, 3], 2);

//Mutations 
//return TRUE if string on first arg contains elements from 2nd arg

function mutation(arr) {
  var strZz1 = arr[0].toLowerCase().split("");
  var strZz2 = arr[1].toLowerCase().split("");
  var countZz = 0;
  
  for (var z = 0; z < strZz2.length; z++ ){
    if(strZz1.indexOf(strZz2[z]) > -1) {
      countZz++;
    }
  }
  if (countZz == strZz2.length){
    return true;
  }
    
    else {return false;}
}

mutation(["hello", "hey"]);

//Falsy Bouncer
// filter out falsy values

function bouncer(arr) {
  return arr.filter(Boolean);
  // Don't show a false ID to this bouncer.
}

bouncer([7, "ate", "", false, 9]);

//Seek and Destroy 
//remove all elements from initial array that are the same from args
function destroyer() {
  var arr = arguments[0];
  var params = [];

  // Create array of all elements to be removed
  for (var k = 1; k < arguments.length; k++)
    params.push(arguments[k]);
  
  // return all not matching values
  return arr.filter(function(item) {
    return params.indexOf(item) < 0;
  });
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);

//Caesars Cipher
// ZZS ;) 
function rot13(str) { // LBH QVQ VG!

  var total = 0;
  var newArray = [];

  for (var z = 0; z < str.length; z++){
   // total += str.charCodeAt([z]);
    total += newArray.push(str.charCodeAt([z]));

   //control parameters for charcode ie start at A after Z...

  }
  var updatedCodes = [];
  for (var j = 0; j < newArray.length; j++){

    if (newArray[j] < 65){
      total += updatedCodes.push(newArray[j]);
    }
   else if (newArray[j] >= 65 && newArray[j] < 78 ){
      total += updatedCodes.push(newArray[j] + 13);
      }
    else if (newArray[j] >= 78){
      total += updatedCodes.push(newArray[j] - 13);
    }
    //else if (newArray[j] > 90){
      //updatedCodes += (newArray[j] - 91);
    //}
  }
  var finalArray = [];
   for (var x = 0; x < updatedCodes.length; x++ ){
     total += finalArray.push(String.fromCharCode(updatedCodes[x]));
   }
  //CANNOT change 32 because that is a space; 33 exclamation mark

      //return from Char Code

  return finalArray.join('');
}

// Change the inputs below to test
rot13("SERR PBQR PNZC!");




















//v2.0
