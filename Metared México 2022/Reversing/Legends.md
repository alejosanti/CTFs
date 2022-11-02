# Legends
Reversing, 100 points

## Description
![](../images/image11.png)

## Solution
Por la descripción, buscando rapidamente en Google, ya sabemos que se trata de la leyenda de La Llorona, por lo que probamos “la llorona” y “la_llorona” como flags, pero no parece ser la flag.

Por lo tanto, abrimos el archivo adjunto con el bloc de notas de Windows:

![](../images/image5.png)

Por el comienzo del archivo, parece ser un archivo ELF.

Tiramos el comando strings de Linux para ver más información:

![](../images/image13.png)

Por lo visto en las últimas 3 líneas de la imagen, parece hacer algún tipo de comparación con el nombre de la leyenda, supuestamente el valor de la flag.

Intentamos abrirlo con la herramienta Cutter en Linux, un programa que nos permite leer el código Assembler del archivo, y nos dirigimos a la sección “main”:

![](../images/image6.png)

Siguiendo el código, vemos que hace uso de la función “verify” para hacer la comparación que nombramos anteriormente, por lo tanto buscamos el código de esa función:

![](../images/image8.png)

Aquí se encuentra escrita la comparación, caracter a caracter, que realiza, por lo que decodificamos todos los caracteres que tiene escrito en hexadecimal con CyberChef:

![](../images/image16.png)

Y obtenemos el valor de la flag, reto completado.

![](../images/image10.png)
