---
title: Project Euler - Problema 1
author: Abel Martinez
date: 2020-06-12 22:00:00 -0500
categories: [Programming, Tutorial]
tags: [programming, project euler]
math: true   
---

## Introduccion a la serie de Project Euler
Esta serie de post esta hecha para documentar mi camino mientras intento resolver los famosos problemas propuestos por el sitio web [Project Euler](https://projecteuler.net/ "projecteuler.net") en el lenguaje de programacion *Python*, aunque proximamente tambien planeo replicarlos con algun lenguaje mas de bajo nivel como *Rust* o *Go*. Esta es mi primera 'serie' que estare escribiendo y espero poder estarla actualizando constantemente.
Primero que nada, quiero aclarar que esta serie de articulos no sera ningun tutorial *basico* de Python, es decir asumire que el lector esta comodo con los fundamentos del lenguaje y mas que nada me concentrare en el *algoritmo* para la resolucion del problema. 
## Problema 1: Multiplos de 3 y 5
**Ingles**
> If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
Find the sum of all the multiples of 3 or 5 below 1000.

**Espanol**
> Si listamos todos los numeros naturales menores de 10 que son multiplos de 3 o de 5 obtenemos 3, 5, 6 y 9. La suma de estos multiplos es 23. Ecuentra la suma de  todos los multiplos de 3 o de 5 menores de 1000

Bueno como primer comentario, he de decir que este problema es muy comun entre paginas de desafios de programacion como *Codewars* y afines, ya que pone a prueba nuestros conocimientos basicos de un lenguaje de programacion como lo son operadores, ciclos y condicionales.

### El operador modulo
Como mencione antes, este problema pone a prueba nuestro conocimiento sobre las funciones basicas de un lenguaje de programacion, en mi caso siendo este *Python*. 
Separando el problema por partes, quizas nuestro primer cometido deberia ser averiguar como car***s podemos verificar, en codigo, que un numero es divisble por otro. Para esto, usaremos a nuestro amigo `%`, mejor conocido como el operador modulo. 

#### Como funciona el operador modulo
Cuando nosotros dividimos dos numeros enteros, siempre nos queda una ecuacion como la siguiente:

$$ {a\over b} = mq + r $$

siendo \\(q \\) el cociente y \\(c\\) el residuo. Entonces, lo que hace el operador modulo es que nos regresa el residuo de cualquier division. 

**Ejemplos**

```python
5 % 2 # Nos da 1, ya que 5 = 2(2) + 1

4 % 2 # Nos da 0, ya que 4 = 2(2) + 0
```

Asi que, como sabemos que un numero es divisble sobre otro? Simplemente tenemos que verificar que el modulo sea 0.

```python
# 5 no es divisble entre 2
5 % 2 == 0 # False

# 4 es divisible entre 2
4 % 2 == 0 # True

# 192 divisble entre 3
192 % 3 == 0 # True
```


### Codigo en Python

Ahora que ya repasamos el uso del operador modulo, creo que estamos listos para pasar al codigo. 

El codigo es el siguiente:

```python
# Creamos una lista para almacenar los multiplos
multiplos = []

# Iteramos sobre todos los numeros menores a 1000, verificamos que sea divisible entre 3 o 5 y los agregamos a la lista
for i in range(1, 1000):   
    if i % 3 == 0 or i % 5 == 0:
        multiplos.append(i)

# Imprimimos en patalla la suma de nuestra lista de multiplos.
print(sum(multiplos))

# Respuesta: 233168
```

El codigo de arriba es muy simple, creamos una lista, iteramos sobre los numeros del 1 a 999 y agregamos los que sean divisibles entre 3 o 5. Al final aprovechamos la funcion integrada de Python `sum` para obtener la suma. Al final obtenemos la respuesta que es **233168**

Este problema es realmente sencillo, al menos en Python, pero nos ayuda a cimentar nuestros conocimientos basicos de cualquier lenguaje de programacion.

