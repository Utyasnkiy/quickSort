# quickSort

import java.util.Arrays;
public class Main {
    public static void main(String[] args) {
        int[] input = {45,32,12,32,45,78,41,25,63,98,-89,-87,-54,-41,32,-84};
        int low = 0;
        int high = input.length - 1;
        System.out.println("Заданный массив");
        System.out.println(Arrays.toString(input));
        Random(input, low, high);
        System.out.println("Отсортированный массив");
        System.out.println(Arrays.toString(input));
        max(input, low, high);
        System.out.println("Отсортированный массив");
        System.out.println(Arrays.toString(input));
        Min(input, low, high);
        System.out.println("Отсортированный массив");
        System.out.println(Arrays.toString(input));
        med(input, low, high);
        System.out.println("Отсортированный массив");
        System.out.println(Arrays.toString(input));
    }
    public static void change(int[] arr, int a, int b){
        int temp = arr[a];
        arr[a] = arr[b];
        arr[b] = temp;
    }
    public static void Random(int[] input, int low, int high) {
        if (input.length == 0)
            if (low >= high)
                return;
        int mid = (int) (low + Math.random()*(high-low));
        int reference = input[mid];
        int i = low, j = high;
        while (i <= j) {
            while (input[i] < reference) {
                i++;
            }
            while (input[j] > reference) {
                j--;
            }
            if (i <= j) {
                change(input, i, j);
                i++;
                j--; }
        }
        if (low < j)
            Random(input, low, j);

        if (high > i)
            Random(input, i, high);
    }
    public static void Min(int[] input, int low, int high) {
        if (input.length == 0)
            if (low >= high)
                return;
        int mid = low;
        int reference = input[mid];
        int i = low, j = high;
        while (i <= j) {
            while (input[i] < reference) {
                i++;
            }
            while (input[j] > reference) {
                j--;
            }
            if (i <= j) {
                change(input, i, j);
                i++;
                j--; }
        }
        if (low < j)
            Min(input, low, j);

        if (high > i)
            Min(input, i, high);
    }
    public static void max(int[] input, int low, int high) {
        if (input.length == 0)
            if (low >= high)
                return;
        int mid = high;
        int reference = input[mid];
        int i = low, j = high;
        while (i <= j) {
            while (input[i] < reference) {
                i++;
            }
            while (input[j] > reference) {
                j--;
            }
            if (i <= j) {
                change(input, i, j);
                i++;
                j--;
            } }
        if (low < j)
            max(input, low, j);
        if (high > i)
            max(input, i, high);
    }
    public static void med(int[] input, int low, int high) {
        if (input.length == 0)
            if (low >= high)
                return;
        int middle = low + (high - low) / 2;
        int reference = input[middle];
        int i = low, j = high;
        while (i <= j) {
            while (input[i] < reference) {
                i++;
            }
            while (input[j] > reference) {
                j--;
            }
            if (i <= j) {
                change(input, i, j);
                i++;
                j--; }
        }
        if (low < j)
            med(input, low, j);
        if (high > i)
            med(input, i, high);
    }
}
