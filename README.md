# assignment-2
import java.util.Scanner;
public class vihecle 
{
	int	licence;//number of vihecle
	int types;
	int entertime;
	int outtime;
	public vihecle(){}
    public float putMoney(int types,String licence,int entertime, int outtime){
        float money = 0;
        if(types==0){
            newenergy b=new newenergy();
            money = (outtime - entertime)*b.unitprice0();
        }
        else if(types==1){
            car c=new car();
            money = (float) ((outtime - entertime)*c.unitprice1());
        }
        else if(types==2){
            bus d=new bus();
            money = (float) ((outtime - entertime)*d.unitprice2());
        }
        else {
            lorry e=new lorry();
            money = (float) ((outtime - entertime)*e.unitprice3());
        }
        return money;
        
    }    

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        while(true){
            vihecle a=new vihecle();
            //listvihecle.add(a);
            System.out.println("types(0/1/2/3),licence,entertime，outtime：");
            int types= scan.nextInt();
            String licence = scan.next();
            int enterTime = scan.nextInt();
            int outtime = scan.nextInt();
            System.out.println(" types ：" +types +" ,licence: " +licence + " ,entertime：" +enterTime +" ,o'clock "+ "，outtime："+outtime +" ,o'clock ");
            float amoney = a.putMoney(types,licence,enterTime, outtime);
            System.out.println("your must pay：");
            System.out.println(amoney + "euro");
        }
    }    
    
    

}
class newenergy extends vihecle
{
     public int unitprice0(){
        return 0;
    }

}
class car extends vihecle
{
     public int unitprice1(){
        return 1;
    }

}
class bus extends vihecle
{
     public int unitprice2(){
        return 2;
    }

}
class lorry extends vihecle
{
     public int unitprice3(){
        return 3;
    }

}
