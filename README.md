# Mod-17-assigment
Mod-17-assigment

<h1>REGEX (regular expression) Guide</h1>
  


## Description
In this guide you will learn how utilize regex! This tutorial uses javascript code on  and its output. <br/>

 ## Table Of Contents : 
 1.  [Title](#title)
 2.  [Description](#description)
 3.  Tables
        1.  [Modifiers](#modifiers) 

        2.  [Sets](#sets)

        3.  [Metacharacters](#metacharacters)

        4.  [Quantifiers](#quantifiers)   

        5.  [Groups](#groups) 

        6.  [Assertions](#assertions)

 4.  [search() without Regex](#search1)
 5.  [search() with Regex](#search2)
 6.  [replace()](#replace)
 7.  [test()](#test)
 8.  [exec()](#exec)
 9.  [About Me](#about-me) 


## Modifiers
<a id="modifiers"></a>
Modifiers are regex that indicates the matche it needs to do, with the help of shorthands.
| Modifier      | Description |
| ----------- | ----------- |
| i   | Case-insensitive matching |
| g   | Global match |
| m   | ^ and $ start and end of the multi line matching  |
| a   | Matched ASCII only  |
| L   | Locale character classes   |
| s   | Matches evrything including newline as well    |
| u   | Matches unicode character classes   |
| x   | Allow spaces and comments    |

## Sets
<a id="sets"></a>
Sets are used to select certain characters with regex. Sets can be identified in square brackets.
| Modifier | Description | Code | Output | 
| ----------- | ----------- | ----------- | ----------- |
| [abc]   | Matches any of a (or) b (or) c. It does not match abc | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "Yes this is amazing isn't it";`<br>  `let result = text.match(/[ia]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> i,i,a,a,i,i,i</pre> |
| [a-p]   | Matches any alphabet from a-p | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "abcdefghijklmnopqrstuvwxyz";`<br>  `let result = text.match(/[a-p]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p</pre> |
| [A-Z]   | Matches any alphabet in Capital from A-Z  | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "AbCdEfGhIjKlMnOpQrStUvWxYz";`<br>  `let result = text.match(/[A-Z]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> A,C,E,G,I,K,M,O,Q,S,U,W,Y</pre> |
| `[a\-p]`  | Matches a, -, or p. It matches – because \ escapes it.  | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "abcdefghijklmnopqrstuvwxyz-";`<br>  `let result = text.match(/[a\-p]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> a,p,-</pre> |
| [-z]   | Matches – or z   | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "abcdefghijklmnopqrstuvwxyz----";`<br>  `let result = text.match(/[-z]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> z,-,-,-,-</pre> |
| [a-p0-9]   | 	Matches characters from a to p or from 0 to 9. | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "abcdefghijklmnopqrstuvwxyz095";`<br>  `let result = text.match(/[a-p0-9]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p,0,9,5</pre> |
| [(+*)]   | Special characters become literal inside a set, so this matches (, +, *, or ) | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "abcd(efgh+ijklmnopqr**stuvwxyz-)))";`<br>  `let result = text.match(/[(+*)]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> (,+,*,*,),),)</pre> |
| [^ab5]  | Adding ^ excludes any character in the set. Here, it matches characters that are not a, b, or 5    | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "abcdef5gh+ijkl45-";`<br>  `let result = text.match(/[^ab5]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> c,d,e,f,5,g,h,+,i,j,k,l,4,-</pre> |
| \[i\]   | 	Matches [i] because both parentheses [ ] are escaped  | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "Yes this is amazing isn't it";`<br>  `let result = text.match(/[i]/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> i,i,i,i,i</pre> |

## Metacharacters
<a id="metacharacters"></a>
Metacharacters are regex that indicates the matches it needs to do using shorthands. All metacharacters use "\" infront of them to easily identify them.
| Metacharacter      | Description |
| ----------- | ----------- |
| \w     | Match alphanumeric (a-z, A-Z, 0-9 and underscore(_))   |
| \W     | Match NON alphanumerc other than (not a-z, notA-Z, not0-9, not underscore)   |
| \d     | Match a digit (0-9)  |
| \D     | Match non digit (not 0-9)  |
| \s     | Match whitespace characters with \t, \n, \r and space characters  |
| \S     | Match non-whitespace characters  |
| \A     | Match string to right at absolute start of string whether in single / multiline |
| \Z     | Match string to left at absolute end of string whether in single / multiline |
| \n     | Match a newline character |
| \t     | Match a tab character |
| \b     | Find a match at beginning of word \bdivya or Find a match at end of word divya\b       |
| \B     | Find a match that is non-boundary  |

## Quantifiers 
<a id="quantifiers"></a>
Quantifiers are regex that indicate the number of matches it needs to do.
| Quantifier      | Description | Code | Output |
| ----------- | ----------- | ----------- | ----------- |
| n+     | Match a string with atleast one n  | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "Hellooo World! Hello Divya!";`<br>  `let result = text.match(/o+/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> ooo,o,o</pre> |
| n*   | Match a string with 0 or more occurances of n  | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "Hellooo World, Divya!";`<br>  `let result = text.match(/lo*/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> l,looo,l</pre> |
| n?   | Match a string with 0 or 1 occurance of n   | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "1, 100 or 1000?";`<br>  `let result = text.match(/10?/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> 1,10,10</pre> |

## Groups:
<a id="Groups"></a>
Groups are use for assigning regex to outputs into a partition, you can later retrive the values from each/all group(s). It organizes data into containers and assigns an index, later you can retrieve the values or look at all the values from the groups. The paranthesis indicate groups.
| Expresions      | Description |
| ----------- | ----------- |
| ( )   | 	Matches the expression inside the parentheses and groups it which we can capture as required |
| (?#…)   | Read a comment |
| (?PAB)   | Matches the expression AB, which can be retrieved with the group name.  |
| (?:A)   | 	Matches the expression as represented by A, but cannot be retrieved afterwards.  |
| (?P=group)   | Matches the expression matched by an earlier group named “group”   |

## Assertions:
<a id="assertions"></a>
Assertions are like "if" statements but written in regex syntax. Assertions are identified if there is a "?" in the regex.
| Modifier      | Description | Code | Output |
| ----------- | ----------- | ----------- | ----------- |
| A(?=B)   | This matches the expression A only if it is followed by B. (Positive look ahead assertion) | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";`<br>  `let result = text.match(/A(?=B)/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> A</pre> |
| A(?!B)   | 	This matches the expression A only if it is not followed by B. (Negative look ahead assertion) | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "ACDEFGHIJKLMNOPQRSTUVWXYZ";`<br>  `let result = text.match(/A(?!B)/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> A</pre> |
| (?<=B)A   | 	This matches the expression A only if B is immediate to its left.  (Positive look behind assertion)  | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "BACDEFGHIJKLMNOPQRSTUVWXYZ";`<br>  `let result = text.match(/(?<=B)A/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> A</pre> |
| (?<!B)A   | This matches the expression A only if B is not immediately to its left. (Negative look behind assertion)  | <pre>`<p id="demo"></p>`<br>`<script>`<br>  `let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";`<br>  `let result = text.match(/(?<!B)A/g);`<br>  `document.getElementById("demo").innerHTML = result;`<br>`</script>`</pre> | <pre>> A</pre> |
| ![image](https://github.com/divyakrishnan15/regex_tutorial/assets/40469923/47fc6cfa-47c1-47bb-b829-7605d0112556) | 	If else conditional   | | |

 ## 1. search() without regex:  
 <a id="search1"></a> 
```shell
<!DOCTYPE html>
<html>
<body>

<p>Search a string for "divya", and display the position of the match:</p>

<p id="demo"></p>

<script>
let text = "Hello world"; 
let n = text.search("hello");
document.getElementById("demo").innerHTML = n;
</script>

</body>
</html>
```

Output:
Search a string for "hello", and display the position of the match:

6


 ## 2. search() With a Regular Expression :  
 <a id="search2"></a> 
```shell
<!DOCTYPE html>
<html>
<body>

<p>Search a string for "hello", and display the position of the match:</p>

<p id="demo"></p>

<script>
let text = "Hello world"; 
let n = text.search(/hello/i);
document.getElementById("demo").innerHTML = n;
</script>

</body>
</html>
```

Output:
Search a string for "hello", and display the position of the match:

6


 ## 3. replace():  
 <a id="replace"></a> 
```shell
<!DOCTYPE html>
<html>
<body>

<p>Replace "car" with "bus" in the paragraph below:</p>
<button onclick="myFunction()">Try it</button>
<p id="demo">This is a car</p>

<script>
let text = document.getElementById("demo").innerHTML;
  document.getElementById("demo").innerHTML =
  text.replace(/car/i, "bus");
</script>

</body>
</html>
```

Output:
Replace "car" with "bus" in the paragraph below:

Try it
Please visit bus!

 ## 4. test():  
 <a id="test"></a> 
```shell
<!DOCTYPE html>
<html>
<body>

<p>Search for an "i" in the next paragraph:</p>
<p id="p01">This is a car!</p>
<p id="demo"></p>

<script>
let text = document.getElementById("p01").innerHTML;
const pattern = /i/;
document.getElementById("demo").innerHTML = pattern.test(text);
</script>

</body>
</html>
```

Output:
Search for an "i" in the next paragraph:

This is a car!

true


 ## 5. exec():  
 <a id="exec"></a> 
```shell
<!DOCTYPE html>
<html>
<body>

<p id="demo"></p>

<script>
const obj = /i/.exec("This is a car!");
document.getElementById("demo").innerHTML =
"Found " + obj[0] + " in position " + obj.index + " in the text: " + obj.input;
</script>

</body>
</html>
```

Output:
Found i in position 2 in the text: This is a car!


