package domain;
import java.util.*; //import the Scanner Class
import java.util.HashMap; // import the HashMap class

public class HelloWorld {
//This Code for SinglePhase HomeSector //
    public static void main(String[] args) {

    Scanner input=new Scanner(System.in);
     System.out.println("Enter your Consumption in kwh per month\n");
    double TheAmountOfConsume=input.nextDouble();
    double Value=0;
    double diff=0 ;
    if(1.0 <= TheAmountOfConsume && TheAmountOfConsume <= 160.0){
    Value=TheAmountOfConsume*0.33; 
    }
    
    else if(161<=TheAmountOfConsume  && TheAmountOfConsume <=300){
    diff=(TheAmountOfConsume-160)*0.072    ;
    Value=5.28+diff ;
    }
    
    else if(301<=TheAmountOfConsume  && TheAmountOfConsume <=500){
    diff=(TheAmountOfConsume-300)*0.086    ;
    Value=15.36+diff ;
    }
    
    else if(501<=TheAmountOfConsume && TheAmountOfConsume<=600){
    diff=(TheAmountOfConsume-500)*0.114    ;
    Value=32.56+diff ;
    }
    
    else if(601<=TheAmountOfConsume && TheAmountOfConsume<750){
    diff=(TheAmountOfConsume-600)*0.158  ;
    Value=43.96+diff ;
    }
    
    else if(750<=TheAmountOfConsume && TheAmountOfConsume<1000){
    diff=(TheAmountOfConsume-750)*0.188   ;
    Value=67.66+diff ;
    }
    
    else if (TheAmountOfConsume>=1000){
    diff=(TheAmountOfConsume-1000)*0.265    ;
    Value=114.66+diff ;
    }
double meter =0.2;
double reef=TheAmountOfConsume/1000;
    double DiffFuilPrice ;
    if (TheAmountOfConsume>=300){
        DiffFuilPrice= TheAmountOfConsume*0.01 ;  
    }
    
    else{
        DiffFuilPrice=0;
    }
    double Trash;
     if (TheAmountOfConsume>=200){
        Trash=(((TheAmountOfConsume-200)*5)/1000)+1.67 ;  
    }
    
    else{
        Trash=0;
    }
   double FinalElictricBill=Value+meter+reef+DiffFuilPrice+Trash+1;
  /*  method 1 using HashMaps
  HashMap<String, Double> Bills = new HashMap<String, Double>();
     
      Bills.put("\nConsumption Value ",Value);
      Bills.put("\nMeter Value ", meter);
      Bills.put("\nreef fils Value ",reef);
      Bills.put("\nDiffFuilPrice ",DiffFuilPrice);
      Bills.put("\nTrash Value ",Trash);
   
     System.out.println(Bills); */
     
     //method 2 using Array
     
     String[] Bills={"\nConsumption Value ","\nMeter Value ","\nreef fils Value ","\nDiffFuilPrice ","\nTrash Value "};
     double[] billsValue={Value,meter,reef,DiffFuilPrice,Trash};
     
     for(int i=0;i<=4;i++){
     System.out.println(Bills[i]+" = " +billsValue[i]);
     }
     
     System.out.println("\nThe value of total ElictricBill = "+FinalElictricBill);

}

}