# 버블정렬

## 구현 목록
``` Java
import java.util.Random;
public class Main {
    private static void bubbleSort(int[] arr){ //함수를 받아서 재함수를 호출함
        bubbleSort(arr,arr.length -1); //함수에서 배열의 주소와 정렬이 안된 배열 마지막 인덱스를 넘김
    }

    public static void bubbleSort(int[] arr, int last) {
        if(last > 0){ //마지막 인덱가 0 보다 클 때 까지 재귀호출함
            for(int i = 1; i <=last; i++){ //마지막 인덱스까지 돌림
                if(arr[i-1]>arr[i]){ //arr배열의 앞에 있는 인덱스가 나보다 큰가 비교를 함
                    change(arr,i-1,i); //자리를 바꾸는 함수
                }
            }
            bubbleSort(arr, last -1); // 정렬한 마지막 인덱스를 제외하고 다시 호출
        }
    }

    private static void change(int[] arr, int source, int target) { //자리를 바꾸는 함수
        int temp = arr[source];
        arr[source] = arr[target];
        arr[target] = temp;
    }
    private static void print(int[] arr){ //배열을 출력해주는 함수
        for(int data : arr) {
            System.out.print(data + ", ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] arr = new int[5];
        Random random = new Random();
        for(int i = 0; i<arr.length; i++){ //랜덤 번호 생성
            arr[i] = (int)(Math.random()*50);
        }

        print(arr);
        bubbleSort(arr);
        print(arr);

    }
}
``` 
## 설명
* 램덤으로된 배열을 메소드를 이용하여 정렬 

## Tools
![IntelliJ IDEA](https://img.shields.io/badge/IntelliJ%20IDEA-000000.svg?&style=for-the-badge&logo=IntelliJ%20IDEA&logocolor=white)
## Skill Stack
![Java](https://img.shields.io/badge/Java-FF160B.svg?&style=for-the-badge&logo=Java&logocolor=white)
