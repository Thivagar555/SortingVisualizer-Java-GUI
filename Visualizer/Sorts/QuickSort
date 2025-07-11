package Visualizer.Sorts;

import Visualizer.*;

public class QuickSort implements Runnable{

    private Integer[] toBeSorted;
    private VisualizerFrame frame;
    private boolean fast;

    public QuickSort(Integer[] toBeSorted, VisualizerFrame frame, boolean fast) {
        this.toBeSorted = toBeSorted;
        this.frame = frame;
        this.fast = fast;
    }

    public void run() {
        if (fast) {
            sortFast(0, toBeSorted.length - 1);
        } else {
            sortSlow(0, toBeSorted.length - 1);
        }
        SortingVisualizer.isSorting = false;
    }

    private void sortFast(int low, int high) {
        if (low < high) {
            int pi = partition(low, high);
            sortFast(low, pi - 1);
            sortFast(pi + 1, high);
        }
        frame.reDrawArray(toBeSorted);
        try {
            Thread.sleep(SortingVisualizer.sleep);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }

    private void sortSlow(int low, int high) {
        if (low < high) {
            int pi = partition(low, high);
            sortSlow(low, pi - 1);
            sortSlow(pi + 1, high);
        }
        frame.reDrawArray(toBeSorted);
        try {
            Thread.sleep(SortingVisualizer.sleep);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }

    private int partition(int low, int high) {
        int pivot = toBeSorted[high];
        int i = (low - 1);
        for (int j = low; j < high; j++) {
            if (toBeSorted[j] < pivot) {
                i++;
                int temp = toBeSorted[i];
                toBeSorted[i] = toBeSorted[j];
                toBeSorted[j] = temp;
                frame.reDrawArray(toBeSorted, i, j);
                try {
                    Thread.sleep(SortingVisualizer.sleep);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        }
        int temp = toBeSorted[i + 1];
        toBeSorted[i + 1] = toBeSorted[high];
        toBeSorted[high] = temp;
        frame.reDrawArray(toBeSorted, i + 1, high);
        try {
            Thread.sleep(SortingVisualizer.sleep);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        return i + 1;
    }
}
