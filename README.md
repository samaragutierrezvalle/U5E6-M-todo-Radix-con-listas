# U5E6-M-todo-Radix-con-listas
package radixlistas;

import java.util.ArrayList;
import java.util.List;


public class radixListas {
    
     public static void main(String[] args) {
       List<Integer> lista = new ArrayList<Integer>();
       lista.add(1);
       lista.add(4);
       lista.add(98);
       lista.add(24);
       lista.add(3);
       lista.add(9);
       lista.add(789);
       
       RadixListas obj= new RadixListas();
       obj.radix(lista);
       
  }

    private static void radix(List<Integer> lista ) {
     int x,i,j;
     for(x=Integer.SIZE-1;x>=0;x--){
      List<Integer> auxiliar = new ArrayList<Integer>();
      for(int s=0; s<lista.size();s++){
      auxiliar.add(0);
      }
      j=0;
      for(i=0; i<lista.size();i++){
          boolean mover=lista.get(i)<<x>=0;
          
           if(x==0 ? !mover:mover){
              auxiliar.set(j,lista.get(i));
               j++;
            }
           else{
               lista.set(i-j,lista.get(i));
           }
        }   
        for(i=j;i<auxiliar.size();i++){
          auxiliar.set(i,lista.get(i-j));
      }
      lista=auxiliar;
      }
        System.out.println("esta es la lista ordenada");
         for( j=0;j<lista.size();j++){
          System.out.print(lista.get(j)+" ");
      }
    }
    
    
}
