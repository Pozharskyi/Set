Set
===
package TestPackage;
import java.util.Arrays;

public class Set {
    private int n = 3;
    private int size = 1;
    private int[] arr = new int[n];

    private boolean isInSet;
    private boolean isNotFull;
    
    //добавление элемента
    public  void add(int value){
        isNotFull = false;
        for(int i=0; i<arr.length; i++)  {                   //есть ли элемент в наборе
            if(arr[i] == value){
                isInSet=true;

            }
            if(arr[i] == 0){                                 //есть ли свободное место
                isNotFull = true;
            }
        }
        if(!isNotFull){                                       //увеличение размера на n
            size++;
            int[] tmpArr;
            tmpArr = arr.clone();
            arr = new int[n*size];
            arr = Arrays.copyOf(tmpArr,(n*size));

//            for(int i=0;i<tmpArr.length; i++){
//
//                arr[i] = tmpArr[i];
//            }
            

        }
        for(int i=0; i<arr.length; i++){                          //добавление нового элемента
            if(arr[i]==0 && !isInSet) {
                arr[i] = value;

                break;
            }

            }

    }


    public  int get(int index){                                   //возвращает элемент указанного индекса
        if ((index < 0) || (index > n)) {
            return 0;
        } else {
        return arr[index];
        }
    }
    public  void delete(int value){                                //удаляет указанный элемент
        for(int i=0; i<arr.length; i++){
            if(arr[i]==value){
                arr[i] = 0;
                break;
            }
        }

    }
    public  void update(){                                          //выводит Set
        System.out.println("\n");
        for(int i=0; i<arr.length; i++)  {
            System.out.print(arr[i] + " ");

        }        
    }
    public  boolean contains(int value){                            //проверяет налычие элемента в Set
        for(int i=0; i<arr.length; i++){
            if(arr[i] == value) {
             return(true);

            }
        }
      return false;
    }
}
