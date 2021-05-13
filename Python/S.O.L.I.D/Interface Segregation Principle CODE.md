БЫЛО:
```
interface Shape {
    drawCircle();
    drawSquare();
    drawRectangle();
}
class Circle implements Shape {
    drawCircle(){
        //...
    }
    drawSquare(){
        //...
    }
    drawRectangle(){
        //...
    }    
}
class Square implements Shape {
    drawCircle(){
        //...
    }
    drawSquare(){
        //...
    }
    drawRectangle(){
        //...
    }    
}
class Rectangle implements Shape {
    drawCircle(){
        //...
    }
    drawSquare(){
        //...
    }
    drawRectangle(){
        //...
    }    
}

```


СТАЛО:
```
interface Shape {
    draw();
}

class Circle implements Shape {
    draw() {
        //...
    }
}
class Square implements Shape {
    draw() {
        //...
    }
}
class Rectangle implements Shape {
    draw() {
        //...
    }    
}
class Triangle implements Shape {
    draw() {
        //...
    }
}

```

[[S.O.L.I.D]]
[[Interface Segregation Principle]]