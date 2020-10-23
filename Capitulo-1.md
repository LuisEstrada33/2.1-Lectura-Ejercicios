![](img/Cap1.png)
# 1.1.1. Características generales de la arquitectura ARM
ARM es una arquitectura RISC (Reduced Instruction Set Computer=Ordenador
con Conjunto Reducido de Instrucciones) de 32 bits, salvo la versión del core ARMv8-
A que es mixta 32/64 bits (bus de 32 bits con registros de 64 bits). Se trata de una
arquitectura licenciable, quiere decir que la empresa desarrolladora ARM Holdings
diseña la arquitectura, pero son otras compañías las que fabrican y venden los chips,
llevándose ARM Holdings un pequeño porcentaje por la licencia.
# Registros
La arquitectura ARMv6 presenta un conjunto de 17 registros (16 principales más
uno de estado) de 32 bits cada uno.
# Esquema de almacenamiento
![](img/Esq1.png)
# 1.1.2. El lenguaje ensamblador
El ensamblador es un lenguaje de bajo nivel que permite un control directo de
la CPU y todos los elementos asociados. Cada línea de un programa ensamblador
consta de una instrucción del procesador y la posición que ocupan los datos de esa
instrucción.
# 1.1.3. El entorno
![](img/Ent1.png)
# 1.1.5. Aspecto de un programa en ensamblador
```bash
.data
var1 : .word 3
var2 : .word 4
var3 : .word 0x1234
.text
.global main
main : ldr r1, puntero_var1 /* r1 <- & var1 */
ldr r1, [ r1 ] /* r1 <- *r1 */
ldr r2, puntero_var2 /* r2 <- & var2 */
ldr r2, [ r2 ] /* r2 <- *r2 */
ldr r3, puntero_var3 /* r3 <- & var3 */
add r0, r1, r2 /* r0 <- r1 + r2 */
str r0, [ r3 ] /* *r3 <- r0 */
bx lr
puntero_var1 : .word var1
puntero_var2 : .word var2
puntero_var3 : .word var3
```
