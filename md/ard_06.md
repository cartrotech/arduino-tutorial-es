# 06 - Las salidas analógicas

[img1]: ./../imatges/ard/ard_06_01.png "Señal digital"
[img2]: ./../imatges/ard/ard_06_02.png "Señal analógica"
[img3]: ./../imatges/ard/ard_06_03.png "PWM"
[img4]: ./../imatges/ard/ard_06_04.png "Salidas con PWM"
[img5]: ./../imatges/ard/ard_06_05.png "Esquema de montaje"

## Finalidad

Comprender las diferencias entre analógico y digital. Conocer las salidas cuasi analógicas de Arduino y qué es la modulación por pulsos (PWM).

## Material requerido

|                                 Imagen                                 | Descripción               |
| :--------------------------------------------------------------------: | :----------------------- |
|   <img src="./../imatges/mat/mat_unor3.png" width="50" height="50">    | Arduino Uno o compatible |
| <img src="./../imatges/mat/mat_protoboard.png" width="50" height="50"> | Una protoboard           |
|   <img src="./../imatges/mat/mat_cables.png" width="50" height="50">   | Cables de conexión       |
|    <img src="./../imatges/mat/mat_led.png" width="50" height="50">     | Un diodo led             |
|  <img src="./../imatges/mat/mat_resis330.png" width="50" height="50">  | Una resistencia 330 Ohms |

## Analógico y digital

Todas las señales que hemos trabajado hasta ahora con nuestro Arduino, de
entrada o de salida, tienen una característica común: son digitales, es
decir que pueden tomar un valor ALTO o BAJO, pero no valores intermedios.

Si representamos el valor de una **señal digital** a lo largo del tiempo,
veríamos algo así:

![Señal digital][img1]

En la vida muchas cosas son así, apruebas o suspensos, enciendes la luz o
la apagas, pero muchas otras son variables medibles continuas y pueden
tener cualquier valor que imaginemos, como el ángulo de las agujas del
reloj o la temperatura, que dentro de valores finitos pueden tomar tantos
valores intermedios como podamos imaginar.

A esta clase de variables las llamamos **analógicas** y una
representación por contraposición a lo **digital**, sería algo así:

![Señal analógica][img2]

No es raro que queramos controlar algo del mundo exterior con una
señal analógica de manera que el comportamiento del sistema siga
esa señal. Podemos por ejemplo querer variar la luminosidad de un
diodo LED y no simplemente apagarlo o encenderlo.

En esta lección aprenderemos a enviar señales analógicas a los pines de salida
de Arduino.

## Salidas cuasi analógicas

Hasta ahora hemos visto cómo activar las salidas digitales de Arduino, para
encender y apagar un LED por ejemplo. Pero no hemos visto cómo modificar la
intensidad del brillo de ese LED. Para esto, tenemos que modificar la
tensión de salida de nuestro Arduino, o en otras palabras tenemos que poder
presentar un valor analógico de salida.

Para empezar debemos dejar claro que los Arduino carecen de salidas
analógicas puras que puedan hacer esto (con la notable excepción del
Arduino DUE).

Pero como los chicos de Arduino son listos, decidieron usar un truco,
para que con una salida digital pudiéramos conseguir que casi parezca una
salida analógica.

A este truco se le llama **PWM**, siglas de Pulse Width Modulation, o
**modulación de ancho de pulsos**. La idea básica es poner salidas
digitales que varían de forma muy rápida de manera que el valor eficaz
de la señal de salida sea equivalente a una señal analógica de menor
tensión.

![PWM][img3]

Lo sorprendente es que el truco funciona.

Fíjate en el ancho del pulso cuadrado de arriba. Cuanto más ancho es,
más tensión media hay presente entre los pines, y esto en el mundo
exterior es equivalente a un valor analógico de tensión comprendido entre 0 y 5V. Al 50% es equivalente a una señal analógica del 50% de 5V, es decir 2,5V. Si mantenemos los 5V un 75% del tiempo, será el equivalente a una señal analógica de 75% de 5V = 3,75 V.

Para poder usar un pin digital de Arduino como salida analógica, lo
declaramos en el **Setup()** igual que si fuera digital:

```Arduino
pinMode( 9, OUTPUT) ;
```

La diferencia viene a la hora de escribir en el pin:

```Arduino
digitalWrite(9, HIGH);//Pone 5V en la salida
digitalWrite(9, LOW);//Pone 0V en la salida
analogWrite( 9, V) ;//analogWrite escribe en el pin de salida un valor entre 0 y 5V, dependiendo de V (que debe estar entre 0 y 255).
```

De esta manera si conectamos un LED a una de estas salidas PWM
podemos modificar su brillo sin más que variar el valor que
escribimos en el pin.

Pero hay una restricción. No todos los pines digitales de Arduino aceptan
poner valores PWM en la salida. Solamente aquellos que tienen un símbolo ~
delante del número. Fíjate en la numeración de los pines de la imagen:

![Pines con PWM][img4]

- Solamente los pines 3, 5, 6, 9, 10 y 11 pueden hacer PWM y simular un valor analógico en su salida.
- Si intentas hacer esto con un pin diferente, Arduino acepta la orden tranquilamente, sin error, pero para valores de 0 a 127 entiende que es _BAJO_ y para el resto pone _ALTO_ y sigue con su vida satisfecho con el deber cumplido.

## Modificando el brillo de un LED

Haremos el típico montaje de una resistencia y un diodo LED, similar al de
la lección 2, pero asegurándonos de usar uno de los pines digitales que pueden
dar señales PWM. En la imagen he usado el pin 9.

![Montaje][img5]

Podemos escribir un programa similar a esto:

```Arduino
//Código: ARD_06_01

void setup()
{
    pinMode( 9, OUTPUT) ;
}

void loop()
{
    for ( int i= 0 ; i<255 ; i++)
    {
        analogWrite (9, i) ;
        delay( 10);
    }
}
```

El LED va aumentando el brillo hasta un máximo y vuelve a empezar
bruscamente. Podemos modificar un poco el programa para que la transición
sea menos violenta:

```Arduino
//Código: ARD_06_02

void setup()
{
    pinMode( 9, OUTPUT) ;
}

void loop()
{
    for ( int i= -255 ; i<255 ; i++)
    {
        analogWrite (9, abs(i)) ;
        delay( 10);
    }
}
```

Hemos hecho el ciclo de subir y bajar el brillo del LED con un único
bucle. La función **abs(num)**, retorna el valor absoluto o sin signo
de un número **num**, y por eso mientras que i viaja de -255 a 255,
**abs(i)** va de 255 a 0 y vuelve a subir a 255.

## Conceptos importantes

- Describimos a grandes rasgos la diferencia entre valores digitales y valores
  analógicos.
- Hemos visto cómo simular valores analógicos en una salida digital de
  Arduino.
  - Solo con las salidas que lo aceptan: pines 3, 5, 6, 9, 10 y 11.
  - Podemos asignar valores entre 0 y 255.

## Ver también

- [README](../README.md)
