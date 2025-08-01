# ESTRUCTURA if-else Y switch

## ------Operadores------ ------De\_ \_Comparación------
Al tener la opción de if se puede utilizar para comparaciones con variables o datos que se vayan a utilizar.

#### Ejemplo:
**Operadores de Compilacón**
* "<"  -  Significa menor que.
* ">"  - Significa mayor que.
* "!=" - Significa diferente a.
* "==" - Significa igual a.
* "<=" - Significa menor o igual a.
* ">=" - Significa mayor o igual a.
**Operadores Lógicos**
* "&&"  (AND Lógico) - Ambas condiciones tienen que ser verdaderas.
* "||"  (OR Lógico) - Al menos una condición debe ser verdadera.
* "!"   (NOT Lógico) - Invierte el valo booleano de una condición.

## \_Estructura\_ \_if-else\_
La estructura if-else en C++ es una herramienta fundamental para tomar decisiones en el código. Permite al programa ejecutar diferentes bloques de código dependiendo de si una condición es verdadera o falsa.

Funciona de la siguiente forma:

1. El programa evalúa una condición.
2. Si la condición es **verdadera** se ejecuta el código dentro del bloque "if".
3. Si la condición es **falsa**, se ejecuta el código dentro del bloque "else".

#### Ejemplo de sintaxis:

```
if (condicion) {
    // Código que se ejecuta si la condición es verdadera
} else {
    // Código que se ejecuta si la condición es falsa
}
```

* **Condición**: Es una expresión que debe evaluarse como verdadera (*true*) o falsa (*false*). Puede ser una comparación. Por ejemplo validar si la variable A1 es mayor a 10 (a1 > 10), una variable booleana, o cualquier expresión que resulte en un valor booleano.  
* **Las Llaves {}**: definen los bloques de código. Si solo hay una línea de código dentro del *if* o *else*, las llavesesson opcionales, pero es una buena práctica usarlas siempre para una mayor claridad del proceso que se realiza y evitar errores.

#### Ejemplo 1: Validar si un número ingresado es par o impar
```
#include <iostream>
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

```
#include <iostream>
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

## \_Estructura\_ \_if\_ \_Sin\_ \_else\_
Se puede utilizar una estructura *if* sin un bloque *else* si solo se necesita ejecutar un código cuando la condición es verdadera y no hay nada específico que hacer cuando es falsa.

#### Ejemplo de sintaxis:

```
if (condicion) {
    // Código que se ejecuta si la condición es verdadera
}
// El programa continúa aquí, independientemente de la condición.
```

#### Ejemplo 1: Brindar una bienvenida solo si el usuario es el administrador

```
#include <iostream>
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

## \_Almacenamiento\_ \_if-else\_
Se puede encadenar múltiples condiciones utilizando *else if*. Esto permite evaluar varias condiciones en secuencia. Una vez que una condición es verdadera, su bloque de código se ejecuta y el resto de la cadena *else if-else* se salta.

#### Ejemplo de sintaxis:

```
if (condicion1) {
    // Código si condicion1 es verdadera
} else if (condicion2) {
    // Código si condicion2 es verdadera (y condicion1 fue falsa)
} else if (condicion3) {
    // Código si condicion3 es verdadera (y condicion1 y condicion2 fueron falsas)
} else {
    // Código si ninguna de las condiciones anteriores es verdadera
}
```

#### Ejemplo 1: Calificar Jugador con respecto a una letra

```
#include <iostream>
using namespace std;
int main() {
    int score;
    cout << "Jugador, ingresa tu puntuación (0-100): ";
    cin >> score;
    if (score >= 90) {
        cout << "Tu calificación es A" << endl;
    } else if (score >= 80) {
        cout << "Tu calificación es B" << endl;
    } else if (score >= 70) {
        cout << "Tu calificación es C" << endl;
    } else if (score >= 60) {
        cout << "Tu calificación es D" << endl;
    } else {
        cout << "Tu calificación es F" << endl;
    }
    return 0;
}
```

## \_Estructura\_ \_switch\_

La estructura **switch** es una declaración de control de selección que permite que una variable o expresión sea evaluada contra una lista de valores. Es una alternativa más limpia y eficiente al uso de múltiples declaraciones **if-else if-else** cuando se tiene que tomar decisiones basadas en diferentes valores que puede tomar una sola variable.

**¿Cómo funciona al estructura switch?**

1. **Expresión de switch**: Se evalúa una expresión, que puede ser una variable de tipo entero, carácter o enumeración.
2. **Case**: El valor de la expresión de *switch* se compara con los valores especificados en cada *case*.
3. **Coincidencia**: Si el valor de la expresión coincide con un valor de *case*, el código dentro de ese *case* se ejecuta.
4. **Break**: Se coloca esta palabra de forma obligatoria, ya que define hasta donde finaliza el *case*. Detiene la ejecución del *switch* una vez que se encuentra una coincidencia y el código de ese *case* ha terminado. Si no se coloca *break*, la ejecución caerá al siguiente *case* (esto es conocido como "fall-through"), ejecutando el código de los *case* subsiguientes hasta que encuentra un *break* o el final del *switch*.
5. **Default**: Esta condición es opcional. Si ninguno de los valores del *case* coincide con la expresión de *switch*, el código dentro del bloque *default* se ejecuta. Es similar a la cláusula *else* en un *if-else if*.

#### Ejemplo de sintaxis:
```
switch (expresion) {
    case valor1:
        // Código a ejecutar si expresion == valor1
        break;
    case valor2:
        // Código a ejecutar si expresion == valor2
        break;
    case valor3:
        // Código a ejecutar si expresion == valor3
        break;
    // ... más casos
    default:
        // Código a ejecutar si ninguno de los casos anteriores coincide
        break; // Opcional si es el último bloque
}
```

* **Expresión**: Debe ser un tipo entero, carácter, enumeración o un tipó de clase que tenga un operador de conversación a un tipo entero. No puede ser un tipo de punto flotante (float, double).
* **valor1, valor2, valor3**: Deben ser constantes o expresiones constantes literales. No pueden ser variables.

#### Ejemplo 1: Menú de opciones simples
```
#include <iostream>
using namespace std;
int main() {
    int opcion;
    cout << "Seleccione una opción:" << endl;
    cout << "1. Abrir archivo" << endl;
    cout << "2. Guardar archivo" << endl;
    cout << "3. Imprimir documento" << endl;
    cout << "4. Salir" << endl;
    cout << "Ingrese su opción: ";
    cin >> opcion;
    switch (opcion) {
        case 1:
            cout << "Abriendo archivo..." << endl;
            // Aquí iría el código para abrir un archivo
            break;
        case 2:
            cout << "Guardando archivo..." << endl;
            // Aquí iría el código para guardar un archivo
            break;
        case 3:
            cout << "Imprimiendo documento..." << endl;
            // Aquí iría el código para imprimir
            break;
        case 4:
            cout << "Saliendo del programa. ¡Hasta luego!" << endl;
            break;
        default:
            cout << "Opción no válida. Por favor, intente de nuevo." << endl;
            break;
    }
    return 0;
}
```
**EXPLICACIÓN DEL EJEMPLO**
* El usuario ingresa un número.
* La viriable opçion se evalúa en el switch.
* Si *opcion* es 1, se ejecuta el código del *case 1* y luego con *break* sale del *switch*.
* Si *opcion* es 2, se ejecuta el código del *case 2* y así sucesivamente.
* Si el ususario ingresa un número que no es 1, 2, 3 o 4 se ejecuta el bloque de *default*.


