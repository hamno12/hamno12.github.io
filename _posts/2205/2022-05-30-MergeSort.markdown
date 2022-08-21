---
layout: post
title: 병합 정렬   
date: 2022-05-29 22:43:23 +0900
categories : Algoritm 
---
# 병합 정렬    

> https://gmlwjd9405.github.io/2018/05/08/algorithm-merge-sort.html


This is code
```java
import java.util.Scanner;

public class Main {

    private static int[] tmp;


    public static void main(String[] args) {

        int[] src = new int[]{1, 9, 8, 5, 4, 2, 3, 7, 6};
        Array(src);
    }

    public static void printArray(int[] src) {
        for (int i = 0;i < src.length; i++){
            System.out.print(src[i] + " ");
        }
    }

    public static void Array(int[] src) {
        tmp = new int[src.length];
        mergeSort(src, 0, src.length-1);
        printArray(src);
    }

    public static void mergeSort(int[] src, int left, int right) {

        if (left < right) {
            int mid = left + (right - left) / 2;
            mergeSort(src, left, mid);
            mergeSort(src, mid+1, right);

            int p = left;
            int q = mid + 1;
            int idx = p;

            while (p <= mid || q <= right) {
                if (q > right || (p <= mid && src[p] < src[q])) {
                    tmp[idx++] = src[p++];
                } else {
                    tmp[idx++] = src[q++];
                }
            }

            for (int i = left; i <= right; i++) {
                src[i] = tmp[i];
            }
        }
    }
}





```
