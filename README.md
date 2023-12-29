# Exam_Z2_Matraieva
import java.util.Arrays;
import java.util.Random;
import java.util.Scanner;

public class MatrixSorting {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Введення розмірності матриці
        System.out.print("Введіть розмірність матриці n: ");
        int n = scanner.nextInt();

        int[][] a = new int[n][n];
        Random random = new Random();

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                a[i][j] = random.nextInt(2 * n + 1) - n;
            }
        }
        // Виведення початкової матриці
        System.out.println("Початкова матриця:");
        printMatrix(a);
        // Введення номеру стовпця (рядка), за яким будемо впорядковувати матрицю
        System.out.print("Введіть номер стовпця (рядка) k: ");
        int k = scanner.nextInt();
        // Впорядкування матриці за вказаним стовпцем (рядком)
        sortMatrixByColumn(a, k);
        // Виведення впорядкованої матриці
        System.out.println("Матриця, впорядкована за " + k + "-м стовпцем (рядком):");
        printMatrix(a);
    }
    private static void printMatrix(int[][] matrix) {
        for (int[] row : matrix) {
            System.out.println(Arrays.toString(row));
        }
    }
    // Метод для впорядкування матриці за заданим стовпцем (рядком)
    private static void sortMatrixByColumn(int[][] matrix, int columnIndex) {
        // Використовуємо Comparator для порівняння рядків матриці
        Arrays.sort(matrix, (row1, row2) -> Integer.compare(row1[columnIndex], row2[columnIndex]));
    }
}
