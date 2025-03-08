# Java.
Java
import java.util.Arrays;

/**
 * OptimizedBubbleSort
 * 
 * This class implements an optimized version of the Bubble Sort algorithm,
 * which reduces unnecessary comparisons by keeping track of the last swapped index.
 */
public class OptimizedBubbleSort {
    public static void main(String[] args) {
        // Sample array
        int[] array = {64, 34, 25, 12, 30, 11, 90};

        // Perform optimized bubble sort
        optimizedBubbleSort(array);

        // Print the sorted array
        System.out.println("Sorted array: " + Arrays.toString(array));
    }

    /**
     * Optimized Bubble Sort algorithm.
     * Reduces the number of comparisons by keeping track of the last swap position.
     * 
     * @param arr The array to be sorted
     */
    static void optimizedBubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped;
        int lastSwappedIndex;

        do {
            swapped = false;
            lastSwappedIndex = 0;

            for (int i = 1; i < n; i++) {
                if (arr[i - 1] > arr[i]) {
                    // Swap arr[i-1] and arr[i]
                    int temp = arr[i - 1];
                    arr[i - 1] = arr[i];
                    arr[i] = temp;
                    swapped = true;
                    lastSwappedIndex = i;
                }
            }
            // Reduce the range for the next pass
            n = lastSwappedIndex;
        } while (swapped);
    }
}
