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
