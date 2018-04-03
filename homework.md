# wk11_dy1_homework

# JS Day 1 Homework
Go through each sample code and work out what the output will be and explain what happened.

### Episode 1
var name = 'Keith';  - name defined (Keith)

var printName = function() {
  console.log('My name is ' + name );  - prints out combined name (Keith) and string
};

printName();  - calls function to print out “My name is Keith”

### Episode 2
score = 5;  - sets score as 5

var result = function() {
  var score = 3;   - set variable within function to 3
  return score;
};

console.log(result()); - calls function to print out score, which is set to 3 within the function; score set to 5 is never used.

### Episode 3
var myAnimals = ['Chickens', 'Cats', 'Rabbits']; - defines “myAnimals” array

var listAnimals = function() {
  myAnimals = ['Ducks', 'Dogs', 'Lions']; - defines “myAnimal” as used within the listAnimals function
  for(var i=0;i<myAnimals.length; i++){
    console.log(i + ": " + myAnimals[i]);
  }
}

listAnimals(); - calls the listAnimals function and uses the “local” instance of myAnimals to output; initial (global) myAnimals Array is not used.

### Episode 4
var suspectOne = 'Jay';
var suspectTwo = 'Val';
var suspectThree = 'Keith';
var suspectFour = 'Rick';  - defines all 4 suspects

var allSuspects = function() {
  var suspectThree = 'Harvey'  defines suspectThre as “Harvey” within the function
  console.log('Suspects include: ' + suspectOne + ', ' + suspectTwo + ', ' + suspectThree + ', ' + suspectFour) - outputs all 4 suspects including “Harvey” as suspectThree
};

allSuspects(); - runs allSuspects function (see comments above)
console.log( 'Suspect three is:' + suspectThree );  - output runs outwith the allSuspects function therefore suspectThree is not “Harvey”. 

### Episode 5
var detective = {
  name : 'Ace Ventura',  - sets name to “Ace Ventura”
  pet : 'monkey'
};

var printName = function(detective) {  - defines “var “printName” as a  function
  return detective.name
};

var detectiveInfo = function() { - defines var detectiveInfo as a functions
  detective['name'] = 'Poirot'   - sets detective.name (same as detective[‘name’]) as ‘Poirot’ within the detectiveInfo function
  return printName(detective);
};

console.log(detectiveInfo());  - outputs the output from the detectiveInfo function (where detective.name is set to ‘Poirot’).

### Episode 6
var murderer = 'rick';  - sets murderer as ‘rick’ (globally)

var outerFunction = function() {
  var murderer = 'marc'; - sets murderer as ‘marc’ within the outerFunction

  var innerFunction = function() {
    murderer = 'valerie'; - sets murderer as ‘valerie’ within the innerFunction
  }

  innerFunction();  - executes innnerFunction.
}

outerFunction();  - executes outerFunction
console.log('the murderer is ', murderer);  outputs murderer as ‘rick’, as those defined in the innerFunction and outerFunction are on available outwit those functions as they are not global.
