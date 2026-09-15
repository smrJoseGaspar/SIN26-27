---
title: Tarea. Sistemas informáticos.
author: José Gaspar Sánchez García
lang: es
---

# Unidad 1. Introducción a los sistemas informáticos.

## Actividad: Configurando un sistema informático

### Contexto

Una empresa de desarrollo de aplicaciones necesita preparar los equipos y servidores para alojar una aplicación multiplataforma. El alumnado deberá trabajar con distintos sistemas de numeración y calcular las necesidades de almacenamiento, memoria y transmisión de datos.

### Temporalización

- **Duración:** 2 sesiones de 55 minutos.
- **Agrupamiento:** parejas.
- **Materiales:** calculadora, ordenador o dispositivo móvil, hoja de actividades y tabla de equivalencias.

### Objetivos

Al finalizar la actividad, el alumnado será capaz de:

- Convertir números entre los sistemas decimal, binario y hexadecimal.
- Interpretar números binarios y hexadecimales en contextos informáticos.
- Diferenciar bit, byte y sus múltiplos.
- Realizar conversiones entre unidades de información.
- Resolver problemas relacionados con almacenamiento, memoria y velocidad de transmisión.
- Justificar los procedimientos utilizados.

## Desarrollo de la actividad

### Parte 1. Sistemas de numeración

El alumnado debe resolver las siguientes cuestiones:

1. Convierte los números decimales a binario y hexadecimal:

   - 25
   - 64
   - 127
   - 200
   - 1024

2. Convierte los siguientes números binarios a decimal:

   - 1010~2~
   - 11001~2~
   - 11111111~2~
   - 1000000000~2~

3. Convierte los siguientes números hexadecimales a decimal:

   - A~16~
   - 1F~16~
   - \(80_{16}\)
   - \(FF_{16}\)
   - \(400_{16}\)

4. Explica por qué el sistema hexadecimal resulta útil para representar información binaria de forma más compacta.

5. Un color se representa en formato RGB mediante tres valores de 8 bits. Expresa en hexadecimal el color formado por:

   - Rojo: 255
   - Verde: 128
   - Azul: 64

   El resultado debe escribirse con el formato habitual `#RRGGBB`.

### Ejercicio 1. Conversiones encadenadas

Convierte las siguientes cantidades al resto de sistemas indicados:

| Número inicial | Conversiones que debes realizar |
|---|---|
| \(173_{10}\) | Binario, octal y hexadecimal |
| \(110101101_2\) | Decimal, octal y hexadecimal |
| \(725_8\) | Decimal, binario y hexadecimal |
| \(3F2A_{16}\) | Decimal, binario y octal |
| \(4095_{10}\) | Binario, octal y hexadecimal |

Debes mostrar el procedimiento utilizado, no solamente el resultado.

---

### Ejercicio 2. Detección y corrección de errores

Un estudiante ha realizado las siguientes conversiones. Indica cuáles son incorrectas, corrígelas y explica el error cometido.

1. \(10110110_2 = 176_{10}\)
2. \(2F_{16} = 45_{10}\)
3. \(347_8 = 231_{10}\)
4. \(11110000_2 = E0_{16}\)
5. \(100000000_2 = 256_{10}\)
6. \(7B_{16} = 123_{10}\)

---

### Ejercicio 3. Representación con un número fijo de bits

Representa los siguientes números utilizando exactamente **8 bits**, completando con ceros a la izquierda cuando sea necesario:

- 13
- 58
- 127
- 128
- 200
- 255

Después:

1. Indica cuál es el mayor número natural que puede representarse con 8 bits.
2. Explica por qué el número 256 no puede representarse con 8 bits sin aumentar el número de posiciones.
3. ¿Cuántos valores distintos pueden representarse con 12 bits?

---

### Ejercicio 4. Operaciones binarias y hexadecimales

Realiza las siguientes operaciones. Comprueba el resultado convirtiéndolo a decimal:

1.  
   \[
   101101_2 + 11011_2
   \]

2.  
   \[
   11001010_2 - 101101_2
   \]

3.  
   \[
   3A_{16} + 2F_{16}
   \]

4.  
   \[
   B4_{16} - 3D_{16}
   \]

5.  
   \[
   1011_2 \times 110_2
   \]

---

### Ejercicio 5. Direcciones y posiciones de memoria

Un microcontrolador utiliza direcciones de memoria de **16 bits**.

1. ¿Cuántas direcciones diferentes puede representar?
2. ¿Cuál es la primera dirección y cuál es la última expresadas en hexadecimal?
3. Convierte a decimal las direcciones:

   - `0x00FF`
   - `0x1000`
   - `0x7FFF`
   - `0xA000`
   - `0xFFFF`

4. Si cada dirección identifica un byte, ¿cuál es la capacidad máxima de memoria direccionable?
5. Expresa dicha capacidad en bytes, KiB y MiB.

---

### Ejercicio 6. Máscaras de bits

En una aplicación, un byte almacena el estado de ocho dispositivos. Cada bit puede tener el valor:

- `1`: dispositivo activado.
- `0`: dispositivo desactivado.

El estado actual es:

```text
10110110
```

1. ¿Qué dispositivos están activados si el bit menos significativo corresponde al dispositivo 0?
2. Expresa el estado en hexadecimal.
3. Se desea activar el dispositivo 0 sin modificar el estado de los demás. ¿Qué operación lógica debe realizarse?
4. Se desea desactivar el dispositivo 4. ¿Qué máscara utilizarías?
5. Calcula el resultado final de cada operación.

Puedes utilizar las operaciones lógicas AND, OR, XOR y NOT.

---

### Ejercicio 7. Interpretación de un color RGB

Una aplicación almacena los colores utilizando tres componentes de 8 bits: rojo, verde y azul.

Para cada uno de los siguientes colores:

```text
#3A7FD2
#FF8800
#12C040
#8040FF
```

1. Separa el código en sus componentes rojo, verde y azul.
2. Convierte cada componente hexadecimal a decimal.
3. Representa cada componente en binario utilizando 8 bits.
4. Indica cuál de los colores tiene mayor intensidad de azul.
5. Calcula el valor decimal total de los 24 bits correspondientes al color `#3A7FD2`, considerando el código hexadecimal completo como un único número.

---

### Ejercicio 8. Análisis de una cabecera hexadecimal

Los primeros bytes de un archivo aparecen representados de la siguiente manera:

```text
89 50 4E 47 0D 0A 1A 0A
```

1. Convierte cada byte hexadecimal a decimal.
2. Convierte cada byte a binario utilizando 8 bits.
3. Calcula cuántos bits ocupa toda la secuencia.
4. Interpreta la secuencia hexadecimal como un único número y conviértela a decimal.
5. Investiga qué tipo de archivo utiliza habitualmente esta firma hexadecimal y explica para qué sirve una firma de archivo.

Este ejercicio permite relacionar los sistemas de numeración con la identificación de archivos informáticos.

---

### Ejercicio 9. Problema de codificación

Una aplicación utiliza códigos de caracteres de 8 bits.

1. ¿Cuántos caracteres diferentes pueden representarse?
2. ¿Cuántos bits serían necesarios para representar 1.000 símbolos distintos?
3. Representa en binario y hexadecimal los valores decimales correspondientes a los caracteres:

   - 65
   - 66
   - 67
   - 97
   - 98
   - 99

4. Si los valores 65, 66 y 67 corresponden a las letras `A`, `B` y `C`, ¿qué palabra se representa mediante la secuencia?

```text
48 4F 4C 41
```

5. Convierte la secuencia completa a binario.

---

### Ejercicio 10. Reto integrador

Un sistema registra la siguiente información en un campo de 16 bits:

```text
1010110011010110
```

Resuelve las siguientes cuestiones:

1. Divide el número en dos grupos de 8 bits.
2. Convierte el valor completo a hexadecimal.
3. Convierte el valor completo a decimal.
4. Calcula qué porcentaje de los bits son iguales a `1`.
5. Indica qué dispositivos estarían activos si cada bit representara un indicador independiente.
6. Si los 4 bits más significativos representan un código de prioridad, ¿qué prioridad tiene el sistema?
7. Si los 4 bits menos significativos representan el número de errores detectados, ¿cuántos errores se han registrado?
8. Propón una interpretación razonable para los 8 bits centrales.

## Propuesta de evaluación específica

Esta parte puede calificarse sobre 10 puntos:

- Conversiones entre bases: **2 puntos**.
- Representación fija en bits: **1 punto**.
- Operaciones binarias y hexadecimales: **2 puntos**.
- Direccionamiento y memoria: **1,5 puntos**.
- Máscaras y operaciones lógicas: **1,5 puntos**.
- Interpretación de colores, archivos o caracteres: **1 punto**.
- Reto integrador y justificación: **1 punto**.

Se puede exigir que, además del resultado, el alumnado indique siempre:

1. La base de origen y la base de destino.
2. El procedimiento utilizado.
3. El resultado con la notación correspondiente, por ejemplo, \(1010_2\), \(12_{10}\) o \(A_{16}\).
4. Una comprobación mediante una conversión alternativa o mediante una operación inversa.



### Parte 2. Unidades de medida de la información

Para esta actividad se utilizarán las siguientes equivalencias:

- 1 byte = 8 bits
- 1 KiB = 1024 bytes
- 1 MiB = 1024 KiB
- 1 GiB = 1024 MiB
- 1 TiB = 1024 GiB

El alumnado debe resolver:

1. Expresa las siguientes cantidades en bytes:

   - 16 bits
   - 4 KiB
   - 2 MiB
   - 3 GiB

2. Convierte:

   - 4096 bytes a KiB.
   - 5 MiB a KiB.
   - 2 GiB a MiB.
   - 1 TiB a GiB.

3. Una aplicación ocupa 750 MiB. El equipo de desarrollo dispone de un disco de 256 GiB. ¿Cuántas copias completas de la aplicación podrían almacenarse, suponiendo que todo el disco está disponible?

4. Cada imagen utilizada por una aplicación ocupa 2,5 MiB. La aplicación contiene 480 imágenes. ¿Cuánto espacio ocupan en total en MiB y en GiB?

5. Un archivo de vídeo ocupa 1,2 GiB. ¿Cuántos archivos de ese tamaño pueden almacenarse en una tarjeta de 16 GiB?

6. Una conexión transmite datos a 100 Mb/s. ¿Cuánto tiempo tardará, aproximadamente, en transmitir un archivo de 500 MB? Para simplificar, se despreciarán las pérdidas y la sobrecarga de la red.

### Parte 3. Reto final: informe técnico

Cada pareja debe elaborar un breve informe para la empresa que contenga:

- Las conversiones realizadas.
- Los cálculos necesarios para determinar el espacio ocupado por la aplicación.
- Una recomendación sobre la capacidad mínima de almacenamiento que debería tener el servidor.
- Una explicación de la diferencia entre:

  - **Mb y MB**
  - **GB y GiB**
  - **bit y byte**

El informe puede presentarse en formato PDF, documento de texto o presentación breve. Debe incluir las operaciones, no solo los resultados.

## Producto final

Cada pareja entregará:

1. La hoja de ejercicios resuelta.
2. Un informe técnico de una o dos páginas.
3. Una explicación oral de tres minutos sobre uno de los problemas planteados.

## Evaluación

| Criterio                                                       | Porcentaje |
| -------------------------------------------------------------- | ---------: |
| Conversiones entre decimal, binario y hexadecimal              |       25 % |
| Conversiones entre unidades de información                     |       20 % |
| Resolución de problemas prácticos                              |       25 % |
| Justificación de los procedimientos y uso correcto de unidades |       15 % |
| Presentación del informe y exposición oral                     |       10 % |
| Trabajo cooperativo y participación                            |        5 % |

### Rúbrica

| Nivel            | Descripción                                                                                                                                     |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Excelente**    | Realiza correctamente las conversiones, muestra las operaciones, utiliza las unidades de forma precisa y justifica sus respuestas con claridad. |
| **Adecuado**     | Resuelve la mayoría de los ejercicios correctamente, aunque presenta algún error menor de cálculo o notación.                                   |
| **Básico**       | Comprende parcialmente los procedimientos, pero comete varios errores y necesita apoyo para resolver los problemas.                             |
| **Insuficiente** | No diferencia los sistemas de numeración ni las unidades de información y no muestra procedimientos válidos.                                    |

## Instrumentos de evaluación

- Hoja de ejercicios.
- Rúbrica del informe técnico.
- Lista de control para la exposición.
- Observación del trabajo en parejas.
- Autoevaluación individual.

### Autoevaluación final

Cada estudiante responderá individualmente:

1. ¿Qué conversión me ha resultado más sencilla?
2. ¿Qué diferencia hay entre un bit y un byte?
3. ¿En qué situaciones se utiliza el sistema hexadecimal?
4. ¿Qué error he cometido y cómo lo he corregido?
5. ¿Qué aspecto necesito seguir practicando?

### Posible ampliación

Como actividad adicional, el alumnado puede analizar la capacidad real de un disco comercial anunciado como “500 GB” y compararla con la capacidad que muestra el sistema operativo en GiB. De este modo se introduce la diferencia entre las unidades decimales del fabricante y las unidades binarias utilizadas habitualmente por los sistemas informáticos.
