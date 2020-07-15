## BOX MODEL

margin - border - padding - content

<img src="box-model.png" width=400>

### BOX-SIZING

#### 1. content-box

- overall box size will be cumulated
- it is the default box-sizing

```
<div
style="background-color:red;
padding:10px;
border:solid 5px black;
width: 100px;"
>
  Content
</div>
```

<div style="background-color:red; padding:10px; border:solid 5px black; width: 100px;">
  Content
</div>

```
actual div width = 100px
overall div width = 130px
```

#### 2. border-box

- overall box size will be equal to actual size
- it is preferred to use border-box

```
<div
style="background-color:red;
padding:10px;
border:solid 5px black;
width: 100px;
box-sizing: border-box;"
>
  Content
</div>
```

<div style="background-color:red; padding:10px; border:solid 5px black; width: 100px; box-sizing: border-box;">
  Content
</div>

```
actual div width = 100px
overall div width = 100px
```

## CUMULATIVE VS COLLAPSING MARGIN

### CUMULATIVE

- margin-right and margin-left sums up

```
<span style="background-color:red; margin-right:5px;">div1</span>
<span style="background-color:blue; margin-left:10px;">div2</span>
```

<span style="width:50px;background-color:red; margin-right:5px;">div1</span>
<span style="width:50px;background-color:blue; margin-left:10px;">div2</span>

```
margin between div1 and div2 is 5px + 10px = 15px
```

### COLLAPSING

- margin-bottom and margin-top collapse to greater one

```
<div style="background-color:red; margin-bottom:5px;">div1</div>
<div style="background-color:blue; margin-top:10px;">div2</div>
```

<div style="width:50px;background-color:red; margin-bottom:5px;">div1</div>
<div style="width:50px;background-color:blue; margin-top:10px;">div2</div>

```
margin between div1 and div2 is 10px
10px is greater than 5px
```

## EM vs REM font-size

### EM

- relative to direct or nearest parent
- increases or decrease font-size by product relative to parent font-size

```
<body style="font-size:1em;">
1 em font-size
  <div style="font-size:2em">
  2 em font-size                      <!-- 1x2 -->
    <div style="font-size:2em">
    4 em font-size                    <!-- 2x2 -->
      <div style="font-size:2em">
      8 em font-size                  <!-- 4x2 -->
      </div>
    </div>
  </div>
</body>
```

<body style="font-size:1em;">
1 em font-size
  <div style="font-size:2em">
  2 em font-size
    <div style="font-size:2em">
    4 em font-size
      <div style="font-size:2em">
      8 em font-size
      </div>
    </div>
  </div>
</body>

### REM

- relative to html root
- increases or decrease font-size by product relative to root font-size

```
<body style="font-size:1rem;">
1 em font-size
  <div style="font-size:2rem">
  2 em font-size                      <!-- 1x2 -->
    <div style="font-size:4rem">
    4 em font-size                    <!-- 1x4 -->
      <div style="font-size:8rem">
      8 em font-size                  <!-- 1x8 -->
      </div>
    </div>
  </div>
</body>
```

<body style="font-size:1rem;">
1 rem font-size
  <div style="font-size:2rem">
  2 rem font-size
    <div style="font-size:4rem">
    4 rem font-size
      <div style="font-size:8rem">
      8 rem font-size
      </div>
    </div>
  </div>
</body>
