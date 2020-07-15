## CSS3 - Cascading Style Sheet

### STYLE PLACEMENT

#### 1. Inline Style

- style within html tags as attribute
- better for quick testing
- not recommended in production

```
<p style="color: red;"> ... </p>
```

#### 2. Head Style

- style within a `<head>` tag
- uses `<style>` tag
- used to override external styles

```
<head>
  <style>
    p {
      color: red;
    }
  </style>
</head>
```

#### 3. External Style

- style sheet in separate file in `.css` extension
- linked using `<link>` tag inside `<head>`
- preferred way

```
<head>
  <link rel="stylesheet" href="styles.css">
<head>
```

### SELECTORS

#### 1. Element Selector

- select by element name

```
p {
  /* ... */
}

h1 {
  /* ... */
}
```

#### 2. Id Selector

- select by element id
- `#` is the prefix

```
#paragraph {
  /* ... */
}
```

#### 3. Class Selector

- select by element class
- `.` is the prefix

```
.container {
  /* ... */
}
```

### COMBINED SELECTOR

- elements can be selected using combined selectors

```
div #button {
  /* ... */
}

.section #button label {
  /* ... */
}
```

### HOW TO SELECT

Single element selection:

- separated by `space`

```
/* space between selectors */

div #red {
  /*
    selects any elements having id 'red' inside div
  */
}
```

- chaining without space defines same element

```

/* no space between selectors */

div#red {
  /*
    selects div elements having id 'red'
  */
}
```

Group selection:

- seperated by `,`

```
div, #container, .wrapper {
  /* ... */
}
```

### STYLE PRIORITY

#### 1. Origin

- last declaration gets priority

```
<head>
  <link rel="stylesheet" href="styles.css">  <!-- first -->

  <style>
    p {
      color: red;   <!-- second -->
    }
  </style>
<head>
<body>

  <p style="color: blue;"> ... </p>    <!-- last -->

</body>
```

Output:

```
p will have blue color
```

#### 2. Merge

- styling same element at different level gets merged

```
<head>
  <style>
    p {
      padding: 10px;
      color: red;
    }
  </style>
<head>
<body>

  <p style="color: blue;"> ... </p>    <!-- last -->

</body>

```

Output Style:

```
p {
  padding: 10px;
  color: blue;
}
```

#### 3. Inheritance

- most of the parent styles are inherited to all child and grandchild elements

```
<head>
  <style>
    body{
      color: blue;
    }
    p {
      padding: 10px;
    }
  </style>
<head>
<body>
  <p> ... </p>
</body>
```

Output

```
p will have blue color
```

#### 4. Specificity

Note: Highest the specificity, highest the priority

<img src="spec.svg" width=100%>

Specificity Calculation:

```
.container p { /*...*/ }

| inline | ids | classes | elements |
| 0      | 0   | 1       | 1        |

Specificity = 11
```

```
#container .hero { /*...*/ }

| inline | ids | classes | elements |
| 0      | 1   | 1       | 0        |

Specificity = 110
```

```
div .hero p { /*...*/ }

| inline | ids | classes | elements |
| 0      | 0   | 1       | 2        |

Specificity = 12
```
