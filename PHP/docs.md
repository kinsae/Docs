## INTRODUCTION TO PHP

### PHP - Hypertext Pre-processor

- Scripting and programming language
- derivative of `C`
- included between:

  ```
  <?php ... ?>       // common, long and most used form [recommended]

  <?= $variable ?>  // echo contents of variable. short form.
                      [should be enabled in php.ini]
  ```

### Variables

- data type assigned to variable depending on what value it holds

  ```
  $num = 10;                      // integer
  $double = 12.22                 // float, double
  $string = "hello";              // or 'Hello' string
  $arr = array();                 // array. linear (index), associative (key=>value)s
  $arr = [];                      // array >php 5.4
  ```

### Array

- Linear array

  ```
  $arr = array('a', 'bc', 'd', 'e');
  $arr = ['a', 'bc', 'd', 'e'];       // >php 5.4
  $var = $arr[0];                     // $var = a;
  ```

- Associative array

  ```
  $arr = array('k1'=>'a', 'k2'=>'bc', 'k3'=>'d', 'k4'=>'e');
  $arr = ['k1'=>'a', 'k2'=>'bc', 'k3'=>'d', 'k4'=>'e'];       // >php 5.4
  $var = $arr['k1'];                                          // $var = a;
  ```

### Output

- `echo`

  - accepts one parameter with parenthesis `()`
  - accepts multiple parameters if used without parenthesis `()`
  - doesn't display `false`. nothing on screen

  ```
  echo("hello");          // () is optional
  echo 'hello';           // '...' doesn't allow variables directly
                          // cannot include /n, /r
  echo "hello";           // "..." allows variable to be included
  echo "hello $var /n";   // valid with double("") quote
                          // can include /n, /r
  echo "hello", $var;     // two parameters
  ```

- `print`

  - accepts only one parameter
  - doesn't display `false`. nothing on screen

  ```
  print("hello");          // () is optional
  print "hello";
  ```

- `print_r()`

  - requires parenthesis `()`
  - display more info about some variables like array
  - doesn't display `false`. nothing on screen

  ```
  print_r('hello');       // hello
  $var = array('a');
  print_r($var;           // Array ( [0] => a )
  ```

- `var_dump() `

  - dump/ display information about different variables
  - the information holds `type`, `length` and `value` of the variable
  - also show info about `false`

  ```
  $a = 32;
  var_dump($a);                           // int(32)

  $b = "Hello world!";
  var_dump($b);                           // string(12) "Hello world!"

  $c = 32.5;
  var_dump($c);                           // float(32.5)

  $d = array("red", "green");
  var_dump($d);                          // array(2)
                                            { [0]=> string(3) "red" [1]=> string(5) "green"}

  var_dump(false);                      // boolean(false)
  ```

### Comments

```
// this is a single line comment

# this is a single line comment

/* this is
  a multi-line
  comment
*/

```

### Expressions

- Increment/ Decrement `++`, `--`

  ```
  // Post increment
  $a = 0;
  echo $a++;    // 0
                // gives what $a holds and then increments by 1

  // Pre increment
  $b = 0;
  echo ++$b;    // 1
                // increments by 1 to $a and gives the value
  ```

- String concatenation `.`

  ```
  echo "hi"." you";   // hi you
  ```

- Equality `==`, `!=`

  - php has implicit `type conversion`. converts values from one type to another when needed.

  ```
  1 == 1;       // true
  1 == true     // true. true is converted to 1
  0 == '0'      // true. '0' is converted to 0
  0 == false    // true. false is converted to 0
  ```

- Identity `===`, `!==`

  - prevents php from doing type conversion
  - checks if value and type is identical

  ```
  1 === 1     // true
  1 === '1'   // false. numeric 1 is not equal to string '1'
  ```

- Ternary `(condition) ? true-statement : false-statement`

  - single line `if else`

  ```
  1>0 ? 'yes' : 'no';
  ```

- Side-effect assignment `+=`, `-=`, `.+` ...

  ```
  $var += 1;        // $var = $var + 1
  $str .= 'a';      // $str = $str . 'a'
  ```

### Type Conversion/Casting

- php does aggressive implicit type conversion, also called casting
- we can make type conversion explicit with casting operators `(int)`, `(string)`

  ```
  $a = 2 + '3';        // + is numeric operator. '3' is converted to numeric 3
                      // Output: 5
  $b = 4/3;            // / results to floating value
                      // Output: 1.3333
  $c = 'a' . 3         // . is string operator. 3 is converted to '3'
                      // Output: a3

  // Casting operator
  $a = 2 + (int) '3';   // (int) converts string '3' into integer 3
                        // Output: 5
  ```

## PHP Global Variables

### \$\_GET

- holds the url variables in array sent through GET request

  ```
  https://example.com?id=2

  <?php echo $_GET['id']; ?>      // 2
  ```

### \$\_POST

- holds the form data in array sent through POST request
- takes `name` and `value` of form inputs

  ```
  <form>
  <input type="text" name="pass" value="pas123">
  <input type="submit" name="add">
  </form>

  <?php echo $_POST['pass']; ?>     // pass123
  ```

### \$\_REQUEST

- combines $_GET and $\_POST
- includes GET url data and POST form-data

  ```
  $_REQUEST['id'];
  $_REQUEST['pass']
  ```

### \$\_SESSION

- used to create and fetch session value
- created sessions are stored in array

  ```
  $_SESSION['id'] = 2;      // creating session of name 'id'

  echo $_SESSION['id'];     // fetch session value of name 'id'
  ```

### \$\_COOKIE

- all created cookies are stored in array
- used to fetch created cookie value

```
$_COOKIE['name'];       // gives value stored in this cookie
                        // 'name' cookie should already be created.
```
