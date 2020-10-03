# Repaso COTI 3102

## Capitulo 8 - Arreglos multidimensionales

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
  
  ```

  

## Capitulo 9 - Clases y Objetos

## Capitulo 10 - Programacion orientada a objetos
