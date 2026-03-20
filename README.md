Examen de programación avanzada
I. (20 PUNTOS) CONCEPTOS
 * ¿Qué imprime el siguiente código?
   int v[] = {10, 20, 30};
int *p = v;
cout << *(p + 1);

   * [ ] a. 10
   * [ ] b. 20
   * [ ] c. Una dirección de memoria
   * [ ] d. 30
   <details>
   <summary>Respuesta</summary>
   Opción (b). *(p + 1) accede al segundo elemento del arreglo, que es 20.
   </details>
 * ¿Cuál es la forma correcta de recorrer e imprimir p, usando notación de apuntadores, dadas las declaraciones y asignaciones del punto 1?
   * [ ] a. for (int i=0; i<3; i++) cout << p[i];
   * [ ] b. for (int i=0; i<3; i++) cout << *(p+i);
   * [ ] c. for (int i=0; i<3; i++) cout << *p;
   * [ ] d. for (int i=0; i<=3; i++) cout << p;
   <details>
   <summary>Respuesta</summary>
   Opción (b). Es la sintaxis correcta de aritmética de punteros para acceder a los valores iterando con i.
   </details>
 * Dado int numeros[5];, ¿qué muestra por pantalla el siguiente código?
   cout << numeros << endl;

   * [ ] a. El valor del primer elemento del arreglo
   * [ ] b. La dirección de memoria del primer elemento
   * [ ] c. El listado de elementos del arreglo
   * [ ] d. Genera error, no se puede imprimir por consola sin un índice
   <details>
   <summary>Respuesta</summary>
   Opción (b). Al usar el nombre del arreglo sin índices, este decae en un puntero a su primer elemento, imprimiendo su dirección de memoria.
   </details>
 * En C++, los archivos binarios permiten acceso aleatorio a los datos mientras que los archivos de texto solo permiten acceso secuencial.
   * [ ] a. Verdadero
   * [ ] b. Falso
   <details>
   <summary>Respuesta</summary>
   Opción (a). Los archivos binarios permiten saltar a diferentes posiciones de bytes exactas con funciones como seekg o seekp, facilitando el acceso aleatorio.
   </details>
 * ¿Cuál es el problema en el siguiente código?
   int *p = new int;
*p = 10;
p = new int;
*p = 20;
delete p;

   * [ ] a. No hay ningún problema, el código es correcto
   * [ ] b. Se produce una fuga de memoria (memory leak)
   * [ ] c. Se intenta acceder a memoria liberada
   * [ ] d. El operador delete no se puede usar con punteros
   <details>
   <summary>Respuesta</summary>
   Opción (b). Se pierde la referencia a la primera asignación de memoria dinámica (*p = 10;) sin haber usado delete, causando una fuga de memoria.
   </details>
 * ¿Qué estructura se usaría preferentemente para almacenar información de estudiantes con nombres, apellidos y calificaciones?
   * [ ] a. Un arreglo simple
   * [ ] b. Una matriz
   * [ ] c. Un struct
   * [ ] d. Un apuntador
   <details>
   <summary>Respuesta</summary>
   Opción (c). Un struct agrupa lógicamente datos de diferentes tipos (cadenas de texto, enteros/flotantes) bajo una sola unidad.
   </details>
 * ¿Qué resultado produce el siguiente código?
   char str[] = "Hola";
cout << *(str + 2);

   * [ ] a. H
   * [ ] b. o
   * [ ] c. l
   * [ ] d. a
   <details>
   <summary>Respuesta</summary>
   Opción (c). La aritmética *(str + 2) accede al índice 2 de la cadena, que corresponde a la letra 'l'.
   </details>
 * Dado el siguiente código, ¿qué ocurrirá?
   int *p = new int[10];
delete p;

   * [ ] a. Se libera correctamente la memoria
   * [ ] b. Se lanza una excepción std::bad_alloc
   * [ ] c. Puede haber fuga de memoria o comportamiento indefinido
   * [ ] d. El compilador detecta el error y no permite compilar
   <details>
   <summary>Respuesta</summary>
   Opción (c). Al asignar un arreglo dinámico con new[], se debe liberar con delete[]. Usar delete produce comportamiento indefinido.
   </details>
 * ¿Cuál es la diferencia entre delete y delete[] en C++?
   * [ ] a. delete se usa para liberar memoria de un solo apuntador, delete[] para arreglos dinámicos
   * [ ] b. No hay diferencia, ambos se pueden usar indistintamente
   * [ ] c. delete solo se usa con punteros a objetos, delete[] con punteros a estructuras
   * [ ] d. delete[] libera más memoria que delete aunque se usa indistintamente
   <details>
   <summary>Respuesta</summary>
   Opción (a). delete es para un solo bloque de memoria reservado con new, mientras que delete[] es para múltiples bloques continuos reservados con new[].
   </details>
 * En un arreglo de apuntadores, cada elemento puede apuntar a diferentes ubicaciones de memoria no contiguas.
   * [ ] a. Verdadero
   * [ ] b. Falso
   <details>
   <summary>Respuesta</summary>
   Opción (a). Un arreglo almacena múltiples punteros, y cada puntero es independiente y puede apuntar a direcciones de memoria completamente distintas y no secuenciales.
   </details>
II. (80 PUNTOS) PARTE PRÁCTICA
Una prestigiosa librería especializada lo ha contratado para crear un sistema que les permita manejar las compras que hacen sus clientes.
La librería maneja un catálogo que es una serie de libros (un arreglo dinámico de Libros) que se almacena de forma permanente en un archivo libros.dat y que se carga en memoria al iniciar el sistema. La librería también tiene la cantidad de libros.
Cada Libro cuenta un Id (entero), un título (arreglo de 100 caracteres), un precio (int) y una cantidad existente llamada inventario (int).
La librería maneja también un conjunto de Compras (a manera de un arreglo dinámico de Compras). Cada Compra tiene un cliente (en particular, su nombre – arreglo de 100 caracteres – y su ID – entero –) y un conjunto de Líneas de compra (arreglo dinámico de Líneas), así como el número de líneas y valor total de la compra (float).
Cada Línea consiste en un id de libro comprado, el título del libro, la cantidad de libros de la línea y el subtotal de línea (float) que corresponde a la multiplicación de la cantidad de libros de la línea por el precio del libro (el precio se busca en el catálogo de libros por id de libros).
El valor total de la compra se calcula como: suma de los subtotales de líneas más el 19 % de IVA.
Archivos utilizados
 * libros.txt (texto, enviado por proveedor)
 * libros.dat (binario, almacenamiento permanente de libros)
 * compras.dat (binario, almacenamiento de compras)
 * compraCliente.txt (archivo plano generado como recibo de compra)
Comportamiento del sistema
 * El archivo libros.dat se crea a partir del archivo libros.txt.
 * Al iniciar el programa, libros.dat debe cargarse en memoria.
 * El usuario puede realizar una compra agregando múltiples líneas.
 * En la línea de compra sólo se pueden agregar libros que existan en el catálogo y tengan cantidad suficiente disponible (inventario).
 * Al agregar una línea de compra, en memoria debe descontarse el inventario del libro en el catálogo. El inventario de cada libro debe ser consistente tanto en libros.dat como en el arreglo dinámico de libros.
 * Al finalizar la compra: se calcula el total, se genera compraCliente.txt y se guarda (al final) la compra en compras.dat.
Como desarrollador, lo han contratado a usted para que implemente un conjunto de funcionalidades listadas a continuación:
1. (5 puntos) Definir en código, las estructuras de Compra, Librería, Línea y Libro.

2. (10 puntos) Escriba una función que cree libros.dat a partir de la información de los libros almacenada en libros.txt, un ejemplo de la sintaxis del archivo es la siguiente.
3
El cantar del condor
101,50000,8
#
Cuentos de los Hermanos Chibcha
123,2500,15
#
La revolucin de los prvulos
345,18000,20
#

> NOTA: La primera línea corresponde al número de libros a leer. A partir de la segunda línea, aparece el título del libro y, en la línea siguiente, los datos de cada libro, separados por comas (ID, precio y cantidad existente). El carácter # indica el fin de ese libro.
> 
(Espacio para respuesta)
3. (10 puntos) Escriba una función que busque un libro por título en el catálogo y retorne: un apuntador al libro si existe o NULL si no existe. Llega como parámetro la librería y el título del libro. Suponga que el título de libro es único y NO se repite.
(Espacio para respuesta)
4. (25 puntos) Escriba una función que permita agregar una Línea a una Compra dentro de la librería. La función recibe la librería, la compra, el título del libro y la cantidad de libros a comprar en esa línea. Si el libro existe en el catálogo de la librería y si la cantidad disponible es suficiente, se crea la línea y se adiciona en el arreglo dinámico de Líneas de la Compra; igualmente, se debe disminuir (en la cantidad comprada) el inventario del libro en el catálogo (en el arreglo dinámico de libros). Finalmente, se debe calcular y modificar el subtotal de la línea que se agrega. Si el libro no existe se muestra un mensaje al usuario. Note que, si se agrega la línea de la compra, se debe incrementar el número de líneas de la compra.
(Espacio para respuesta)
5. (10 puntos) Escriba una función que permita calcular el total de la compra: sumar subtotales e incrementar la suma en un 19 % que corresponde al IVA, y guardar el resultado en el total de la compra. Llega como parámetro la compra (como parámetro por referencia).
(Espacio para respuesta)
6. (10 puntos) Escriba una función que recibe una compra existente y genera un archivo compraCliente.txt con los datos que se muestran en el ejemplo a continuación.
Cliente de la compra: Luz Ramos
ID del cliente: 222333

Lineas de compra (libros vendidos)

Titulo                             Cantidad   Precio      Subtotal
El cantar del condor               3          $50.000     $150.000
Ojos azules                        2          $10.000     $20.000
Nacho lee                          4          $12.000     $48.000
Las tablas de multiplicar          3          $7.000      $21.000

Valor total (con IVA): $284.410


7. (10 puntos) Escriba una función que le permita guardar una compra en el archivo de compras.dat; note que la función recibe la Compra existente.

Restricciones: no se pueden usar variables globales, no se pueden utilizar datos de tipo string. Los arreglos deben ser dinámicos y deben recorrerse con aritmética de apuntadores. Adicione los parámetros que considere necesarios.
