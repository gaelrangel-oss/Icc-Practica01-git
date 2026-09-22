# Icc-Practica01-git
Practica Icc
##Preguntas iniciales
##¿Que informacion almacena un commit?
La vercion modificada del archivo, antes de la vercion final
##¿Que diferencia existe entre un repositorio local y un repositorio remoto?
Un repositorio local se almacena unicamente en un dispositivo mientras el remoto puede ser almacenado en diferentes dispositivos
##¿Que esperan que ocurra cuando ambos integrantes modifican archivos distintos?
Que se cree una nueva version para cada archivo
##¿Que esperan que ocurra cuando ambos modifican exactamente la misma linea?
Se crean dos verciones del archivo en la misma linea, del archivo modificado

##Comandos observados
-git status
-git commit
-git add
-git push
-git pull
-git fetch
-nano

##Planeaciòn
-Developer A debera modificar el archivo con nano/cat
-Developer A debera verificar los cambios con "git status"
-Developer A debera agregar el archivo con "git add" y posteriormente verificarlo con "git diff"
-Developer A debera hacer el commit con "git commit -m "archivo" y verificar con "git status"
-Developer A debera subir el archivo con "git push"
-Developer B debera descargar la actualizacion con "git fetch" y "git pull"

##Historial Esperado

A---B--C--D <- README.md
/
E--G <-Binario.md
/
F--H <-Decimal.md
##Historial Real
H--I---   <--Conflicto Binario
/      \
D--E--   \   <--Conflicto Decimal
/      \  \
A--B--C-L -M    <--Main
/      /  /
F--G---  /   <--Conflicto Decimal
/       /
J--K---     <--Conflicto Binario

1. ¿En que se parece al dibujo inicial?
En que se crearon dos ramas mas.
2. ¿En que es diferente?
En el nombre de las ramas,y ahora hay dos "merge".
3. ¿Que partes del historial no habían anticipado?
Que ibamos a unir las ramas, y que cada archivo no es una rama.
4. ¿Que entienden ahora que no entendían cuando realizaron el primer dibujo?
Cada archivo no crea una rama, se puede trabajar en ramas personales sin afectar a la rama main.
##Respuestas
1. ¿Por qué Git rechazo el primer push de Developer B?
Git rechazó el push porque antes de poder hacer un push se debe estar sincronizado con el repositorio remoto.
2. ¿Existía un conflicto de contenido?
Si, porque el Developer B no tenía la modificación en la copia local
3. ¿Qué ocurrió cuando ejecutaron pull?
Developer A descargó la modificación del Developer B y viceversa.
4. ¿Qué diferencia observan entre un push rechazado y un conflicto?
El push rechazado se debio a que el repositorio tenía una modificación que aún no contenia la copia local del Developer B.

##Pregunta
-¿Realizar un merge implica necesariamente que exista un conflicto?
No, por que modificamos distintos archivos y distintas lineas, por lo que no se genero un conflicto.
-También discutan la siguiente afirmación:Un merge no decide que una rama tenga “mayor prioridad” que otra. Intenta integrar ambas historias.
Si, el merge no decide cual es mas importante, si no que busca juntar los cambios para que sucedan al mismo tiempo, en este caso el merge junto los cambios que realizo cada Developer
sin decidir la importancia de cada uno.

##Preguntas reto 15
1. ¿Que representa HEAD en este momento?
Representa el lugar donde existe el conflicto.
2. ¿Que representa el contenido entre «««< y =======?
El texto del cambio del Developer A
3. ¿Que representa el contenido entre ======= y »»»>?
El texto del cambio del Developer B
4. ¿Por que Git no pudo decidir automáticamente que contenido conservar?
Porque no puede decidir cual tiene prioridad, y da a elegir cual conservar.

##Pregunta reto 19
¿Que ventaja tiene utilizar el nombre v1.0 para identificar este punto del
historial en lugar de utilizar solamente el hash del commit?
Que nos facilita la identificacion del punto del historial.

##Reflexion final
1. ¿Que información almacena un commit?
El conjunto de cambios subidos en el repositorio local.
2. ¿Que diferencia existe entre un repositorio local y un repositorio remoto?
El local almacena la informacion en el dispositivo, mientras el remoto lo hace en un servidor que depende de git.
3. ¿Que ocurrió cuando modificaron archivos diferentes?
Nada, pudimos subir y actualizar los repositorios por que no habia nada que creara un conflicto.
4. ¿Que ocurrió cuando modificaron la misma región de un archivo?
Git mando un conflicto por no poder decidir cual de las dos verciones guardar o priorizar.
5. ¿Que diferencia existe entre commit y push?
Que el comit lo sube al repositorio local, y el push ya lo sube directamente al repositorio remoto.
6. ¿Que función tuvo pull durante la practica?
Descargar/Actualizar los cambios que estaban en el repositorio remoto al local
7. ¿Por que un push puede ser rechazado aunque no exista un conflicto de contenido?
Por no tener los cambios subidos de manera correcta en el commit.
8. ¿Que representa una rama?
Es una "subdivision" de la rama main en la que se puede trabajar sin afectar el contenido de la rama main
9. ¿Que indica HEAD?
La rama en la que se esta trabajando
10. ¿Que hace merge?
Unifica los contenidos de las ramas con la rama principal "main"
11. ¿Por que Git pudo integrar algunos cambios automáticamente y otros no?
Por la existencia de conflictos en los cambios de los archivos, de esta manera no se podìan actualizar
12. ¿Que representan los marcadores «««<, ======= y »»»>?
En un conflicto representan desde donde inicia el conflicto existente y las diferentes versiones de lo que se modifico son representados con los ===== las flechas hacia la derecha representan el final del conflicto
13. ¿Que ventaja proporciona un tag?
Facilita el identificar el momento del historial para conocer en que momento estàs
14. ¿Como cambio su interpretación de los diagramas de historial después de utilizar git log
Descubrimos que la rama main contiene todos los archivos y que no era una rama por archivo, ademàs de que notamos que las ramas y sus combinaciones son mas visibles asi
–graph –oneline –all?
