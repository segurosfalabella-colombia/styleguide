# Estructura de código

[https://github.com/ryanmcdermott/clean-code-javascript#table-of-contents]  
[https://code.tutsplus.com/tutorials/top-15-best-practices-for-writing-super-readable-code--net-8118]  
[https://github.com/johnpapa/angular-styleguide]  

### 1. Utilizar notación camelCase para los nombres de variables, funciones, etc. Primera letra en minúscula)

Incorrecto
```
var respuesta_servidor;
function resolver_ecuacion(){
    //...
}
```

Correcto
```
var respuestaServidor;
function resolverEcuacion(){
    //...
}
```

### 2. El nombre de las funciones y variables debe ser claro y explicar su funcionalidad, la declaración debe empezar con minúsculas.  

Incorrecto
```
var respuesta = true;
function Ecuacion (){
    //...
}
```

Correcto
```
var respuestaServidor = true;
function resolverEcuacion (){
    //...
}
```
### 3. Las constantes deben ser declaradas y con nombre en mayúscula.  

Incorrecto
```
var euler = 2.718281828459045235;
console.log(3.1416);
console.log(euler);
```
Correcto
```
var PI = 3.1416;
var EULER = 2.718281828459045235;
console.log(PI);
console.log(EULER);
```

### 4. Utilizar notación Pascal para clases. (Primera letra mayúscula)  

Incorrecto
```
class  ejemploClase(){
    //...
}
```
Correcto
```
class  EjemploClase(){
    //...
}
```
### 5. Utilizar plurales y singulares para las variables.  

Incorrecto
```
var  fruta = ['Mango', 'Pera', 'Piña'];
frutas.forEach((a) => {
    console.log(a);
});
```
Correcto
```
var  frutas = ['Mango', 'Pera', 'Piña'];
frutas.forEach((fruta) => {
    console.log(fruta);
});
```
### 6. No repetir el nombre de un objeto en sus propiedades.  

Incorrecto
```
var frutas = {
    pera: {
        color_fruta: 'verde',
        sabor_fruta: 'dulce'
    },
    limon: {
        color_fruta: 'verde',
        sabor_fruta: 'acido'
    }
};
```
Correcto
```
var frutas = {
    pera: {
        color: 'verde',
        sabor: 'dulce'
    },
    limon: {
        color: 'verde',
        sabor: 'acido'
    }
};
```
### 7. Nivel de abstracción de las funciones debe ser igual a 1 (Una acción por función) 

Incorrecto
```
function calcularDistanciaMetros(puntoA, puntoB){
    var deltaX = puntoA.x - puntoB.x;
    var deltaY = puntoA.y - puntoB.y;
    var distancia = Math.sqrt(Math.pow(deltaX,2) +Math.pow(deltaY,2));
    var distanciaMetros = distancia * 100;
    return distanciaMetros;
}
```
Correcto
```
function calcularDistanciaMetros(puntoA, puntoB){
    var distancia = calcularDistancia(puntoA, puntoB);
    return centimetrosAMetros(distancia);
}
function calcularDistancia(puntoA, puntoB){
    var deltaX = puntoA.x - puntoB.x;
    var deltaY = puntoA.y - puntoB.y;
    return Math.sqrt(Math.pow(deltaX,2) +Math.pow(deltaY,2));
}
function centimetrosAMetros(valor){
    return valor * 100;
}
```
### 8. Las funciones deben tener máximo de 4 a 6 líneas, si sobrepasa esta cantidad deberá dividirse en otra función.  
### 9. Indentación constante del código.  
### 10. Evitar nesting mayor a 2.  
### 11. Cada función debe ser testeada por separado.  
