# 08 - Crear gráficas utilizando el puerto serie

[img1]: ./../imatges/ard/ard_08_01.png "Trazador"
[img2]: ./../imatges/ard/ard_08_02.png "Gráfica una variable"
[img3]: ./../imatges/ard/ard_08_03.png "Gráfica dos variables"

## Objetivos

Aprender a usar el **Trazador Serie** para hacer **gráficas** con el IDE de Arduino e incluir **diversas variables** en la gráfica.

## Material requerido

| Imagen                                                               | Descripción               |
| -------------------------------------------------------------------- | ------------------------ |
| <img src="./../imatges/mat/mat_portatil.jpg" width="50" height="50"> | PC                       |
| <img src="./../imatges/mat/mat_cableusb.png" width="50" height="50"> | Cable USB                |
| <img src="./../imatges/mat/mat_unor3.png" width="50" height="50">    | Arduino UNO o compatible |

## Dibujar una gráfica utilizando el Trazador Serie

Ya hemos utilizado muchas veces el monitor serie del IDE para mostrar valores de las variables de nuestro programa. Pero en ciertas ocasiones puede ser útil verlo en forma **de gráfica** en lugar de datos numéricos, por ejemplo, para ver la tendencia de los datos de una forma sencilla y clara.

Resulta que el IDE de Arduino incorpora desde la versión 1.6.6 una herramienta llamada **Trazador Serie** que nos permite precisamente crear gráficas a partir de las variables que le indiquemos. Es muy sencilla de usar y por ahora no ofrece muchas opciones, pero seguramente irán añadiendo características nuevas con nuevas versiones.

Para utilizarla no tenemos que aprender nada nuevo en cuanto a la programación.

Simplemente haremos un programa que muestre un valor por el puerto serie. Puedes
utilizar este pequeño programa que genera números aleatorios cada cierto
tiempo:

```Arduino

void setup()
{
  Serial.begin(9600);
}

void loop()
{
  int valor;
  valor = random(0,100);
  Serial.println(valor);
  delay(250);
}
```

Ahora en lugar de abrir el Monitor Serie, abriremos el Trazador Serie,
que está en la barra de herramientas, justo debajo.

![Trazador][img1]

Y cuando cargamos el programa en la placa, veremos cómo se va generando una
**gráfica** a partir de los valores aleatorios que va tomando la variable.

![Gráfica una variable][img2]

## CÓMO INCLUIR MÁS VARIABLES

La herramienta también nos da la opción de mostrar varias variables a la vez en
la misma gráfica. La manera de hacerlo es también muy sencilla,
simplemente tendremos que enviar las dos variables por el puerto serie pero
utilizando un separador "," entre ellas, y automáticamente las dibujará
en la misma gráfica con un color diferente.

Si añadimos otra variable que tome también valores aleatorios al
programa anterior, el programa quedaría de la siguiente forma:

```Arduino

void setup()
{
  Serial.begin(9600);
}

void loop()
{
  int valor1;
  int valor2;
  valor1 = random(0,100);
  valor2 = random(0,100);
  Serial.print(valor1);
  Serial.print(",");
  Serial.println(valor2);
  delay(250);
}
```

![Gráfica dos variables][img3]

## Resumen de la sesión

Hemos descubierto una nueva herramienta que nos permite hacer **gráficas** fácilmente
desde el mismo IDE de Arduino.

- Sabemos incorporar **diversas variables** a la gráfica.
- Ahora que sabemos que existe esta herramienta y cómo se utiliza, puedes incorporarla a tus proyectos para realizar gráficas de las medidas de sensores, la velocidad de un motor, o lo que se te pase por la mente.

## Ver también

- [README](../README.md)
