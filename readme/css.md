## CSS topic

1. color
2. background
3. border
4. height
5. weight
6. margin
7. padding
8. outline
9. text
10. font
11. display
12. justify
13. align
14. overflow
15. z-index
16. opacity
17. url()
18. hover
19. focous
20. gradient
21. box-shadow
22. blur
23. object fit
24. units
25. translate
26. rotate
27. Animation
28. Responsive style

### Internal css
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        h1{
            color: green;
        }
    </style>
</head>
<body>
<h1>Hello-world</h1>
</body>
</html>
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        h1{
            color: green;
        }
    </style>
</head>
<body>
<h1>Hello-world</h1>
</body>
</html>

### Inline css

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
<h1 style="color: red;">Hello-world</h1>
</body>
</html>
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
<h1 style="color: red;">Hello-world</h1>
</body>
</html>

### External css
#### create a css file in external, and give the name to `(css-file-name).css` as `style.css`
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
<h1>Hello-world</h1>
</body>
</html>
```




## 1.color
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            color: red;
        }
    </style>
</head>
<body>
    <h2>Lorem ipsum dolor sit amet consectetur.</h2>
</body>
</html>
```
## 2.backgorund
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            background: green;
            background-color: aqua;

        }
    </style>
</head>
<body>
    <h2>Lorem ipsum dolor sit amet consectetur.</h2>
</body>
</html>
```
## 3.border
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            border: 2px solid red; 
            border: 2px dashed red;
            border: 2px dotted red;
            border-bottom: 2px solid red;
            border-top: 2px solid red;
            border-right: 2px solid red;
            border-left: 2px solid red;
            border: none;
            
        }
    </style>
</head>
<body>
    <h2>Lorem ipsum dolor sit amet consectetur.</h2>
</body>
</html>
```
## 4.height & weight
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        div{
            height: 100px;
            width: 200px;
            border: 2px solid red;
        }
    </style>
</head>
<body>
    <div></div>
</body>
</html>
```
## 5.text & font
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            text-align: center;
            font-size: 15px;
            font-family: serif;
            font-weight: 500;
            font-style: italic;
        }
    </style>
</head>
<body>
    <h2>Lorem ipsum dolor sit amet.</h2>
</body>
</html>
```
## 6.margin
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            margin: 50px;
            margin-top: 50px;
            margin-bottom: 50px;
            margin-right: 50px;
            margin-left: 50px;            
        }
    </style>
</head>
<body>
    <h2>Lorem ipsum dolor sit amet consectetur.</h2>
</body>
</html>
```
## 7.padding
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            padding: 50px;
            padding-top: 50px;
            padding-bottom: 50px;
            padding-right: 50px;
            padding-left: 50px;
            border: 2px solid red;

        }
    </style>
</head>
<body>
    <h2>Lorem ipsum dolor sit amet consectetur.</h2>
</body>
</html>
```
## 8.outline
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            outline: 2px solid red;
            outline: none;
            
        }
    </style>
</head>
<body>
    <h2>Lorem ipsum dolor sit amet consectetur.</h2>
</body>
</html>
```

## 9.display
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            display: flex;
            display: grid;
            display: block;
            display: inline;
            border: 2px solid red;
            
            
        }
    </style>
</head>
<body>
   <h2>Lorem ipsum dolor sit amet.</h2>
</body>
</html>
```
## 10.justify
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            display: flex;
            justify-content: center;
            justify-content: start;
            justify-content: end;
            justify-content: space-around;
            justify-content: space-between;
            justify-content: space-evenly;
            
            justify-items: center;
            justify-items: start;
            justify-items: end;
            justify-items: space-around;
            justify-items: space-between;
            justify-items: space-evenly;
            
            
            
        }
    </style>
</head>
<body>
   <h2>Lorem ipsum dolor sit amet.</h2>
</body>
</html>
```
## 11.align
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        h2{
            display: flex;
            align-content: center;
            align-content: start;
            align-content: end;
            align-content: space-around;
            align-content: space-between;
            align-content: space-evenly;
            
            align-items: center;
            align-items: start;
            align-items: end;
            align-items: space-around;
            align-items: space-between;
            align-items: space-evenly;
            
            
            
        }
    </style>
</head>
<body>
   <h2>Lorem ipsum dolor sit amet.</h2>
</body>
</html>
```

## 14.overflow
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        div{
            width: 150px;
            height: 70px;
            border: 2px red solid;
            overflow: scroll;
            overflow-x:scroll ;
            overflow-y: scroll;
            overflow: hidden;
        }
    </style>
</head>
<body>
    <div>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem numquam labore veniam.</p>
    </div>
</body>
</html>
```

## 15.z-index
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
      
        .div1{
            background: green;
            position: relative;
            z-index: 1;
            width: 200px;
            height: 200px;
        }
        .div2{
            background: red;
            position: absolute;
            width: 250px;
            height: 250px;
            z-index: -1;
        }
    </style>
</head>
<body>
    <div class="div1"></div>
    <div class="div2"></div>
</body>
</html>
```
## 16.opacity
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
      img{
        width: 250px;
        height: 250px;
        opacity: 0.2;
        opacity: 0.5;
        opacity: 1;
      }
    </style>
</head>
<body>
   <img src="https://static.vecteezy.com/system/resources/previews/024/212/465/non_2x/blue-cat-robot-and-a-boy-watching-the-dusk-sky-free-vector.jpg" alt="">
</body>
</html>
```
## 17.url()
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
      .div1{
        width: 500px;
        height: 500px;
        background: url(https://static.vecteezy.com/system/resources/previews/024/212/465/non_2x/blue-cat-robot-and-a-boy-watching-the-dusk-sky-free-vector.jpg);

    }
    </style>
</head>
<body>
   <div class="div1"></div>
</body>
</html>
```
## 18.hover
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        button{
            width: 200px;
            height: 50px;
            background: #000;
            color: white;
        }
        button:hover{
            background: red;
            color: black;
        }
     
    </style>
</head>
<body>
<button>button</button>

</body>
</html>
```
## 19.focus
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        button{
            width: 200px;
            height: 50px;
            background: #000;
            color: white;
        }
        button:focus{
            background: red;
            color: black;
        }
     
    </style>
</head>
<body>
<button>button</button>

</body>
</html>
```
## 20.gradient
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        button{
            width: 200px;
            height: 50px;
            background-image:linear-gradient(green,blue,red) ;
            background-image:linear-gradient(to right,green,blue,red) ;
            color: white;
        }
        
     
    </style>
</head>
<body>
<button>button</button>

</body>
</html>
```
## 21.boxshadow
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            justify-content: space-around;
            align-items: center;
            height: 100vh;
        }
        div{
            width: 200px;
            height: 200px;
            background: red;
            box-shadow: 1px 1px 60px blue;
        }
        
    </style>
</head>
<body>
    <div ></div>
</body>
</html>
```
## 22.blur
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        div{
            
            background: url(https://static.vecteezy.com/system/resources/previews/024/212/465/non_2x/blue-cat-robot-and-a-boy-watching-the-dusk-sky-free-vector.jpg);
            width: 700px;
            height: 500px;
            display: flex;
            justify-content: center;
            align-items: center;
        
        }
        button{
            width: 250px;
            height: 100px;
            color: black;
            background: transparent;
            backdrop-filter: blur(10px);
        }
        
     
    </style>
</head>
<body>
    <div>

        <button>button</button>
    </div>

</body>
</html>
```
## 23.object-fit
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        div{
            
            
            display: flex;
            justify-content: center;
            align-items: center;
        
        }
        img{
            width: 250px;
            height: 350px;
            object-fit: contain;
            object-fit: cover;
            object-fit: fill;
            border: 2px solid red;
        }
       
     
    </style>
</head>
<body>
    <div>

       <img src="https://static.vecteezy.com/system/resources/previews/024/212/465/non_2x/blue-cat-robot-and-a-boy-watching-the-dusk-sky-free-vector.jpg" 
       width="400" height="500"
       alt="">
    </div>

</body>
</html>
```
## 24.units
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fun coding</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        h2{
            font-size: 4px;
            font-size: 4rem;
            font-size: 4em;
            
        }
       div{
        height: 100vh;
        width: 100vw;
        height: 100svh;
        width: 100svw;
        height: 100lvh;
        width: 100lvw;
        height: 100dvh;
        width: 100dvw;

       }
        
       
     
    </style>
</head>
<body>

      <h2>Lorem ipsum dolor sit amet consectetur.</h2>
        <div></div>
</body>
</html>
```
## 25.translate
```

```
## 🎯 1. CSS Transitions: Smooth Property Changes
What it is: Transitions let you smoothly change CSS properties over time (like color, size, or position) when triggered by an event (e.g., hover).
### 🔧 Mini Project: Hover-to-Grow Button

```
<style>
.button {
  background-color: #3498db;
  color: white;
  padding: 10px 20px;
  transition: transform 0.3s ease, background-color 0.3s ease;
}
.button:hover {
  transform: scale(1.2);
  background-color: #2980b9;
}
</style>
<button class="button">Hover Me</button>
```

#### 🧠 Key Concepts
- transition-property: what changes (e.g., transform, background-color)
- transition-duration: how long the change takes (0.3s)
- transition-timing-function: pacing (ease, linear, ease-in-out)
- transition-delay: wait time before starting
Use case: Great for hover effects, toggles, and subtle UI feedback.
Learn more: W3Schools on CSS Transitions

## 🔄 2. CSS Transforms: Move, Rotate, Scale, Skew
What it is: Transforms let you visually manipulate elements without affecting layout flow.
### 🔧 Mini Project: Rotating Card on Hover


```
<style>
.card {
  width: 200px;
  height: 100px;
  background-color: #f39c12;
  transition: transform 0.5s ease;
}
.card:hover {
  transform: rotate(10deg) scale(1.1);
}
</style>
<div class="card">Hover to Rotate</div>
```

#### 🧠 Key Concepts
- transform: scale(1.2): zooms in
- transform: rotate(45deg): spins
- transform: translateX(50px): moves horizontally
- transform: skewY(20deg): slants
Use case: Interactive cards, image effects, playful UI elements.
Explore examples: FreeFrontend CSS Transform Demos

## 🎬 3. CSS Animations: Keyframe-Based Motion
What it is: Animations use @keyframes to define multiple stages of change, not just start and end.
### 🔧 Mini Project: Bouncing Ball



```
<style>
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-50px); }
}
.ball {
  width: 50px;
  height: 50px;
  background-color: #e74c3c;
  border-radius: 50%;
  animation: bounce 1s infinite ease-in-out;
}
</style>
<div class="ball"></div>
```
#### 🧠 Key Concepts
- @keyframes: defines stages (percentages or from/to)
- animation-name: links to the keyframes
- animation-duration: how long it runs
- animation-iteration-count: how many times (infinite)
- animation-timing-function: pacing
Use case: Loading indicators, attention-grabbing effects, storytelling UI.
Explore more: Prismic’s CSS Animation Examples

### 🧩 How They Work Together
- Transform + Transition: Smoothly animate movement or scaling on hover.
- Transform + Animation: Create looping or complex motion.
- Transition vs Animation: Transitions are event-triggered; animations can run automatically.

### Responsive using mediaQueries 
```
@media (max-width: 1200px) {}
@media (max-width: 1100px) {}
@media (max-width: 1024px) {}
@media (max-width: 991px) {}
@media (max-width: 896px) {}
@media (max-width: 879px) {}
@media (max-width: 780px) {}
@media (max-width: 768px) {}
@media (max-width: 580px) {}
@media (max-width: 450px) {}
@media (max-width: 365px) {}
@media (max-width: 315px) {}
```