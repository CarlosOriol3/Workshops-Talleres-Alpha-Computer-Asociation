# Repaso COTI 3102

## Arreglos multidimensionales

### Ejercicios
- 8.1 (Sum elements row by row) Write a method that returns the sum of all the elements in a specified row in a matrix using the following header:
public static double sumRow(double[][] m, int rowIndex)
```java
class Main {
  public static void main(String[] args) {
    //Declarar el arreglo
    double[][] arr = {{1.5, 2, 3, 4},
                      {5.5, 6, 7, 8},
                      {9.5, 1, 3, 1}};
        
    //Imprimir suma de cada fila
    System.out.println(sumRow(arr, 0));
    System.out.println(sumRow(arr, 1));
    System.out.println(sumRow(arr, 2));
  }

  public static double sumRow(double[][] m, int rowIndex) {
    //Inicializar suma
    double sum = 0;

    //Recorer los elementos de la fila especifica
    for (int i = 0; i < m[rowIndex].length; i++) {
      //sumar los elementos
      sum += m[rowIndex][i];
    }
    //retornar el valor
    return sum;
  }
}
```
- 8.2 (Average the major diagonal in a matrix) Write a method that averages all the numbers in the major diagonal in an n * n matrix of double values using the following header:

   public static double averageMajorDiagonal(double[][] m)
```java
class Main {
  public static void main(String[] args) {
    double[][] arr = {{1, 2, 3, 4.0},
                      {5, 6.5, 7, 8},
                      {9, 10, 11, 12},
                      {13, 14, 15, 16}};
                  
  System.out.println(averageMajorDiagonal(arr));
  }

  public static double averageMajorDiagonal(double[][] m){
    //Inicializar suma
    double sum = 0;

    //inicializar puntero para cambiar de columna
    int j = 0;

    //recorrer las filas del arreglo
    for(int i = 0 ; i<m.length; i++){
      //por cada fila sumarle el respectivo numero en cada cilumna de la diagonal
      sum+=m[i][j];
      j++;
    }

    //Calcular el promedio
    double average = sum/m.length;
    //Retornar el valor
    return average;
  }
}
```

- 8.4 (Compute the weekly hours for each employee) Suppose the weekly hours for all employees are stored in a two-dimensional array. Each row records an employee’s seven-day work hours with seven columns. For example, the following array stores the work hours for eight employees. Write a program that displays employees and their total hours in increasing order of the total hours.

 ```java
  class Main {
  public static void main(String[] args) {
    int[][] employees = {{2, 4, 3, 4, 5, 8, 8},
                         {7, 3, 4, 3, 3, 4, 4}};
    weeklyHours(employees);
  }

  public static void weeklyHours(int[][] arr) {
    //recorrido por filas
    for (int i = 0; i < arr.length; i++) {
      //Inicializar suma POR FILA
      int sum = 0;
      //recorrido por columnas
      for(int j = 0; j < arr[i].length; j++){
        sum += arr[i][j]; 
      }
      //Imprimir resultado de cada fila
      System.out.println("Employee "+(i+1)+": "+sum+" hours");
    }
  }
}
```

- 8.5 (Algebra: add two matrices) Write a method to add two matrices. The header of the method is as follows: 

  public static double[][] addMatrix(double[][] a, double[][] b)

  In order to be added, the two matrices must have the same dimensions and the same or compatible types of elements.

  Write a test program that prompts the user to enter two 2 * 2 matrices and displays their sum.
 ```java
import java.util.Scanner;
import java.util.Arrays;
class Main {
  public static void main(String[] args) {
    //Declarar el scanner para recibir input
    Scanner input  = new Scanner(System.in);

    //mostrar mensaje para recoger input de la primera matriz
    System.out.print("Enter 2x2 matrix: ");

    //Recoger input
    double[] afila1 = {input.nextDouble(),input.nextDouble()};
    double[] afila2 = {input.nextDouble(),input.nextDouble()};

    //mostrar mensaje para recoger input de la segunda matriz
    System.out.print("\nEnter another 2x2 matrix: ");

    //Recoger input
    double[] bfila1 = {input.nextDouble(),input.nextDouble()};
    double[] bfila2 = {input.nextDouble(),input.nextDouble()};

    //Construir los arreglos de dos dimensiones
    double[][] arr1 = {afila1,
                       afila2};
    
    double[][] arr2 = {bfila1,
                       bfila2};

    //Utilizar la funcion para sumarlos
    double[][] suma = addMatrix(arr1,arr2);

    //Mostrarlo en pantalla
    for(int i=0;i<suma.length;i++){
      System.out.println(Arrays.toString(suma[i]));
    }                   

  }

  public static double[][] addMatrix(double[][] a, double[][] b) {
    //declarar el arreglo de resultado
    double[][] result = new double[a.length][a[0].length];

    //llenarlo con las respectivas sumas
    for (int i = 0; i < result.length; i++) {
      for (int j = 0; j < result[i].length; j++) {
        result[i][j] = a[i][j] + b[i][j];
      }
    }
    //retornar el arreglo resultado
    return result;
  }

}
```
- 8.6 (Algebra: multiply two matrices) Write a method to multiply two matrices. The
  header of the method is:

  public static double[][] multiplyMatrix(double[][] a, double[][] b)

   To multiply matrix a by matrix b, the number of columns in a must be the same as the number of rows in b, and the two matrices must have elements of the same or compatible types. 

   Write a test program that prompts the user to enter two 3 * 3 matrices and displays their product. 

```java
import java.util.Scanner;
import java.util.Arrays;
class Main {
  public static void main(String[] args) {
    //Declarar el scanner para recibir input
    Scanner input  = new Scanner(System.in);

    //mostrar mensaje para recoger input de la primera matriz
    System.out.print("Enter 3x3 matrix: ");

    //Recoger input
    double[] afila1 = {input.nextDouble(),input.nextDouble(),input.nextDouble()};
    double[] afila2 = {input.nextDouble(),input.nextDouble(),input.nextDouble()};
    double[] afila3 = {input.nextDouble(),input.nextDouble(),input.nextDouble()};

    //mostrar mensaje para recoger input de la primera matriz
    System.out.print("\nEnter another 3x3 matrix: ");

    //Recoger input
    double[] bfila1 = {input.nextDouble(),input.nextDouble(),input.nextDouble()};

    double[] bfila2 = {input.nextDouble(),input.nextDouble(),input.nextDouble()};

    double[] bfila3 = {input.nextDouble(),input.nextDouble(),input.nextDouble()};
    //Construir los arreglos de dos dimensiones
    double[][] arr1 = {afila1,
                       afila2,
                       afila3};
    
    double[][] arr2 = {bfila1,
                       bfila2,
                       bfila3};

    //Utilizar la funcion para multiplicar las matrices
    double[][] mult = multiplyMatrix(arr1,arr2);

    //Mostrarlo en pantalla
    for(int i=0;i<mult.length;i++){
      System.out.println(Arrays.toString(mult[i]));
    }                   

  }

  public static double[][] multiplyMatrix(double[][] a, double[][] b) {
    //declarar el arreglo de resultado
    double[][] result = new double[a.length][a[0].length];

    //llenarlo con las respectivas multiplicaciones
    //i representa las filas, j representa las columnas, k se utiliza para el proceso de multiplicacion
    for (int i = 0; i < result.length; i++) {
      for (int j = 0; j < result.length; j++) {
        for(int k = 0; k < result[i].length; k++){
          result[i][j] += a[i][k] * b[k][j];
        }
      }
    }
    //retornar el arreglo resultado
    return result;
  }

}
```
 - 8.13 (Locate the smallest element) Write the following method that returns the location of the smallest element in a two-dimensional array.
 public static int[] locateSmallest(double[][] a)

 The return value is a one-dimensional array that contains two elements. These two elements indicate the row and column indices of the smallest element in the two-dimensional array. Write a test program that prompts the user to enter a twodimensional array and displays the location of the smallest element in the array.

```java
import java.util.Scanner;
import java.util.Arrays;
class Main {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    //Recoger numero de filas y columnas
    System.out.println("Enter the numbers of rows and collumns: ");
    int rows = input.nextInt();
    int cols = input.nextInt();

    
    System.out.println("Enter the array: ");
    double[][] arr = new double[rows][cols];

    //Llenar el arreglo con las correctas filas y columnas
    for (int i = 0; i < arr.length; i++){
      for(int j=0; j< arr[i].length;j++){
        arr[i][j] = input.nextDouble();
      }
    }

    //Encontrar la posicion del minimo
    System.out.println("Smallest position: "+ Arrays.toString(locateSmallest(arr)));
  }

  public static int[] locateSmallest(double[][] a){
    //inicializar arreglo de posicion en 0,0
    int[] pos = {0,0};
    
    //inicializar el minimo con el valor que se encuentra en la primera posicion del arreglo
    double min = a[0][0];

    //Recorrer cada elemento del arreglo
    for (int i = 0; i < a.length; i++){
      for(int j=0; j< a[i].length;j++){
        //cambiar el valor del minimo y posicion si es necesario
        if(a[i][j]<min){
          min = a[i][j];
          pos[0] = i;
          pos[1] = j;
        }
      }
    }
    //retornar el arreglo de posicion
    return pos;
  } 

}
```
 - 8.16 (Sort two-dimensional array) Write a method to sort a two-dimensional array using the following header:
public static void sort(int m[][])

```java
import java.util.Scanner;
import java.util.Arrays;

class Main {
  public static void main(String[] args) {
    int[][] arr = {{4, 2},{1, 7},{4, 5},{1, 2},{1, 1},{4, 1}};
    
    //Ordenar
    sort(arr);
    
    //Mostrar filas
    for(int i=0;i<arr.length;i++){
      System.out.println(Arrays.toString(arr[i]));
    }
  }

  public static void sort(int m[][]) {
    //Recorrer una vez por cada una de las filas
    for (int i = 0; i < m.length - 1; i++) {
      for (int j = 0; j < m.length - 1; j++) {

        //Cambiar de posicion si el proximo es menor
        if (m[j][0] < m[j + 1][0]) {
          int[] temp = m[j];
          m[j] = m[j + 1];
          m[j + 1] = temp;
          //Tomar en cuanta si las filas comienzan igual entonces comparamos las columnas
        } else if (m[j][0] == m[j + 1][0]) {
          if (m[j][1] < m[j + 1][1]) {
            int[] temp = m[j];
            m[j] = m[j + 1];
            m[j + 1] = temp;
          }
        }

      }

    }
  }

}
```
- 8.28 (Strictly identical arrays) The two-dimensional arrays m1 and m2 are strictly
identical if their corresponding elements are equal. Write a method that returns true if m1 and m2 are strictly identical, using the following header: 

public static boolean equals(int[][] m1, int[][] m2)

 Write a test program that prompts the user to enter two 3 * 3 arrays of integers and displays whether the two are strictly identical. 
```java
import java.util.Scanner;
import java.util.Arrays;

class Main {
  public static void main(String[] args) {
    //Declarar el scanner para recibir input
    Scanner input  = new Scanner(System.in);

    //mostrar mensaje para recoger input de la primera matriz
    System.out.print("Enter 3x3 matrix: ");

    //Recoger input
    int[] afila1 = {input.nextInt(),input.nextInt(),input.nextInt()};
    int[] afila2 = {input.nextInt(),input.nextInt(),input.nextInt()};
    int[] afila3 = {input.nextInt(),input.nextInt(),input.nextInt()};

    //mostrar mensaje para recoger input de la primera matriz
    System.out.print("\nEnter another 3x3 matrix: ");

    //Recoger input
    int[] bfila1 = {input.nextInt(),input.nextInt(),input.nextInt()};

    int[] bfila2 = {input.nextInt(),input.nextInt(),input.nextInt()};

    int[] bfila3 = {input.nextInt(),input.nextInt(),input.nextInt()};
    //Construir los arreglos de dos dimensiones
    int[][] arr1 = {afila1,
                       afila2,
                       afila3};
    
    int[][] arr2 = {bfila1,
                       bfila2,
                       bfila3};
    
    //Mostrar resultado
    System.out.println(equals(arr1,arr2));
  }

  public static boolean equals(int[][] m1, int[][] m2){
    //Verificar primero si son del mismo tamaño
    if(m1.length != m2.length){
      return false;
    }

    //Verificando elemento por elemento hasta encontrar uno diferente y devolver falso
    for(int i=0;i<m1.length;i++){
      for(int j = 0;j<m1[i].length;j++){
        if(m1[i][j] != m2[i][j]){
          return false;
        }
      }
    }
    //De no encontrar devolver cierto
    return true;
  }

}
```

##  Clases y Objetos

-9.6 (Stopwatch) Design a class named StopWatch. The class contains:
■■ Private data fields startTime and endTime with getter methods.
■■ A no-arg constructor that initializes startTime with the current time.
■■ A method named start() that resets the startTime to the current time.
■■ A method named stop() that sets the endTime to the current time.
■■ A method named getElapsedTime() that returns the elapsed time for the
stopwatch in milliseconds.
Draw the UML diagram for the class then implement the class. Write a test program
that measures the execution time of sorting 100,000 numbers using selection sort.

- StopWatch class:
```java
 import java.util.Date;
class StopWatch{
  private long startTime;
  private long endTime;

  public StopWatch(){
    Date date = new Date();
    this.startTime = date.getTime();
    this.endTime = date.getTime();
  }
  public void start(){
    Date date = new Date();
    this.startTime = date.getTime();
  }
  public void stop(){
    Date date = new Date();
    this.endTime = date.getTime();
  }
  public long getElapsedTime(){
    return (this.endTime - this.startTime);
  }
  public long getStartTime(){
    return this.startTime;
  }
  public long getEndTime(){
    return this.endTime;
  }
}
```
 - main class: 
```java
import java.util.Arrays;

class Main {
  public static void main(String[] args) {
    //inicializar el objeto
    StopWatch time = new StopWatch();

    //comenzar el stopwatch
    time.start();

    //Declarar un arreglo
    int[] arr = {1,12,34,564,5,33,12,22,1,24,56,78,100,22,200,12,1,12,34,564,5,33,12,22,1,24,56,78,100,22,200,12,1,12,34,564,5,33,12,22,1,24,56,78,100,22,200,12,1,12,34,564,5,33,12,22,1,24,56,78,100,22,200,12};

    //Aplicarle selection sort
    selectionSort(arr);

    //imprimir arreglo ordenado
    System.out.println(Arrays.toString(arr));

    //parar el stopwatch
    time.stop();

    //imprimir resultados del stopwatch
    System.out.printf("Tiempo inicial: %d\nTiempo final: %d\nTiempo total: %d\n",time.getStartTime(),time.getEndTime(),time.getElapsedTime());

  }

  //selection sort
  public static void selectionSort(int[] arr){  
        for (int i = 0; i < arr.length - 1; i++)  
        {  
            int index = i;  
            for (int j = i + 1; j < arr.length; j++){  
                if (arr[j] < arr[index]){  
                    index = j;//searching for lowest index  
                }  
            }  
            int smallerNumber = arr[index];   
            arr[index] = arr[i];  
            arr[i] = smallerNumber;  
        }  
    }
}


```


- 10.11 (Geometry: the Circle2D class) Define the Circle2D class that contains:
■■ Two double data fields named x and y that specify the center of the circle
with getter methods.
■■ A data field radius with a getter method.
■■ A no-arg constructor that creates a default circle with (0, 0) for (x, y) and 1
for radius.
■■ A constructor that creates a circle with the specified x, y, and radius.
■■ A method getArea() that returns the area of the circle.
■■ A method getPerimeter() that returns the perimeter of the circle.
■■ A method contains(double x, double y) that returns true if the
specified point (x, y) is inside this circle (see Figure 10.21a).
■■ A method contains(Circle2D circle) that returns true if the specified circle is inside this circle (see Figure 10.21b).
■■ A method overlaps(Circle2D circle) that returns true if the specified circle overlaps with this circle (see Figure 10.21c)

```java
public class Circle2D {
  private double x;
  private double y;
  private double radius;

  public Circle2D() {
    this.x = 0;
    this.y = 0;
    this.radius = 1;
  }

  public Circle2D(double x, double y, double radius) {
    this.x = x;
    this.y = y;
    this.radius = radius;
  }

  public double getArea() {
    return Math.PI * Math.pow(this.radius, 2);
  }

  public double getPerimeter() {
    return (Math.PI * 2 * this.radius);
  }

  public boolean contains(double x, double y) {
    double d = Math.sqrt(Math.pow(x - this.x, 2) + Math.pow(y - this.y, 2));
    if( d < this.radius){
           return true;
         }else{
           return false;
         }
  }

  public boolean contains(Circle2D circle) {
    double d = Math.sqrt(Math.pow(circle.getX() - x, 2) + Math.pow(circle.getY() - y, 2));
    if (d <= Math.abs(this.radius - circle.getRadius())) {
      return true;
    } else {
      return false;
    }
  }

  public boolean overlaps(Circle2D circle) {
    double d = Math.sqrt(Math.pow(circle.getX() - x, 2) + Math.pow(circle.getY() - y, 2));
    if (d <= this.radius + circle.getRadius()) {
      return true;
    } else {
      return false;
    }

  }

  public double getX() {
    return this.x;
  }

  public double getY() {
    return this.y;
  }

  public double getRadius() {
    return this.radius;
  }
}

```