---
layout: page
title: Tecnologías
permalink: /tecnologias/
---

#Tecnologías

Si estuviste leyendo las otras páginas habrás visto que mencionamos bastantes tecnologías diferentes, y eso quizás te parezca interesante, pero quizas te aterre un poco. Así que te contamos un poco mejor cómo viene la mano: 

## Más conceptos, menos circo

En la materia queremos contarte conceptos de arquitectura e implementación de una aplicación concurrente (es decir, cualquier aplicación que sea usada por mas una persona) que nos parecen novedosos y útiles hoy en dia. Y de paso, presentarte algunas tecnologías que no son de laboratorio, sino que se usan en la industria. 

Así que **no vamos a matarte** con 18,5 lenguajes, 40 frameworks, 39 biblotecas, 71 test runners y 3,141516 tipos de cerveza (¡ufa!). Sino que vamos a elegir las 3 o como mucho 4 tecnologías más representativas de lo que queremos explicar. 

## You know nothing, Jon Snow

**Asumimos que vos no sabés nada ni de las tecnologías que vamos a ver, ni de los conceptos**, y de hecho, ni siquiera de concurrencia (mas allá de un vago recuerdo de esos días en que eras joven y cursabas operativos). Así que tranquila/o, vamos a explicar todo lo que vamos a usar (al menos, a un nivel razonable, algunas cosas para leer algún día te mandaremos, esperamos que no te enojes :stuck_out_tongue:)


## A lo' bife'

Ahora sí, que vamos a usar: 

  * **JavaScript** (via [Node.js](https://nodejs.org), alguito de Express y algunas bibliotecas, como Bluebird). Vamos a usarlo para entender
    * CPS
    * Promises
    * y las extensiones reactivas, de las que todos hablan, algunos usan, pocos entienden, y ninguno sabe por qué. O casi.  
  * [Elixir](http://elixir-lang.org/). Lo queremos para entender:
    * actores. Podriiiiiiamos haber usado [Erlang](http://www.erlang.org/) (el papá de toda la movida) pero es un poco áspero, así que vamos por Elixir que es algo así como el Erlang de los 2010: bonito, sencillito, no habla mal de tu mamá. ¿Por qué no Akka y Scala? En clase te contamos.
    * STM. Una forma interesante de manejar la memoria de forma concurrente. La verdad es que nos hubiera encantado ver STM con Clojure (que tiene una de las mejores implementaciones), pero consideramos que meternos con Lisp por unas pocas horas de clase era demasiado. Quizás en otro cuatrimestre. 
  * **Haskell**: ninguna materia de concurrencia que se precie podría hacer caso omiso a las bondades del paradigma funcional. "Te acuerdas de Haskell? Volvió, y en forma de móndas!". No bueno, en serio, lo queremos para entender algunos patrones que están presentes a lo largo de todas las tecnologías e ideas que vimos antes. 
   

Ah, y para que no digan que les mentimos, la primera clase vamos a ver dos líneas de Ruby, para poder comparar con la concurrencia tradicional y después olvidarlas. ¿¿¿O querían ver C???
