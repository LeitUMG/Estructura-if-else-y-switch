# ESTRUCTURA if-else Y switch

## Operadores de Comparación
Al tener la opción de if se puede utilizar para comparaciones con variables o datos que se vayan a utilizar.

#### Ejemplo:

* "<"     Significa menor que 
* ">"     Significa mayor que
* "!="    Significa diferente a
* "=="    Significa igual a
* "<="    Significa menor o igual a
* ">="    Significa mayor o igual a

## Estructura if-else
La estructura if-else en C++ es una herramienta fundamental para tomar decisiones en el código. Permite al programa ejecutar diferentes bloques de código dependiendo de si una condición es verdadera o falsa.

Funciona de la siguiente forma:

1. El programa evalúa una condición.
2. Si la condición es **verdadera** se ejecuta el código dentro del bloque "if".
3. Si la condición es **falsa**, se ejecuta el código dentro del bloque "else".

#### Ejemplo de sintaxis:

```if (condicion) {
    // Código que se ejecuta si la condición es verdadera
} else {
    // Código que se ejecuta si la condición es falsa
}
```

* **Condición**: Es una expresión que debe evaluarse como verdadera (*true*) o falsa (*false*). Puede ser una comparación. Por ejemplo validar si la variable A1 es mayor a 10 (a1 > 10), una variable booleana, o cualquier expresión que resulte en un valor booleano.  
* **Las Llaves {}**: definen los bloques de código. Si solo hay una línea de código dentro del *if* o *else*, las llavesesson opcionales, pero es una buena práctica usarlas siempre para una mayor claridad del proceso que se realiza y evitar errores.

#### Ejemplo 1: Validar si un número ingresado es par o impar
```#include <iostream>
using namespace std;
int main() {
    int n1;
    cout << "Ingresa un número: ";
    cin >> numero;

    if (n1 % 2 == 0) {
        cout << n1 << " es un número par." << endl;
    } else {
        cout << n1 << " es un número impar." << endl;
    }
    return 0;
}
```
En este  ejemplo básico, la *condición* es *n1 % 2 == 0*. El operador utilizado es *%* (llamado módulo o MOD) da el residuo de un adivisión. Si el residuo de *n1* dividido por 2 es 0, siginifica que es un número par.

#### Ejemplo 2: Validar si un estudiante aprobó o reprobó

```#include <iostream>
using namespace std;
int main() {
    double calificacion;
    cout << "Ingresa la calificación del estudiante: ";
    cin >> calificacion;

    if (calificacion >= 61.0) { // Dejando 61.0 como la calificación mínima para aprobar el curso
        cout << "¡Felicidades! Has aprobado Algoritmos." << endl;
    } else {
        cout << "Lo siento, has reprobado Algoritmos. Necesitas estudiar más." << endl;
    }
    return 0;
}
```
En este ejemplo básico la *condición* es *calificacion >= 61.0*. Si la calificación es 61.0 o más el estudiante aprueba el curso.

## Estructura if sin else
Se puede utilizar una estructura *if* sin un bloque *else* si solo se necesita ejecutar un código cuando la condición es verdadera y no hay nada específico que hacer cuando es falsa.

#### Ejemplo de sintaxis:

```if (condicion) {
    // Código que se ejecuta si la condición es verdadera
}
// El programa continúa aquí, independientemente de la condición.
```

#### Ejemplo 1: Brindar una bienvenida solo si el usuario es el administrador

```#include <iostream>
#include <string>
using namespace std;

int main() {
    string rolUsuario = "admin"; // Podría venir de una base de datos o entrada de usuario

    if (rolUsuario == "admin") {
        cout << "Bienvenido, Administrador del sistema." << endl;
    }
    cout << "Accediendo al panel de control..." << endl; // Se ejecuta siempre
    return 0;
}
```