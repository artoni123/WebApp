
import java.util.Scanner;
public class Numrat_detyre2 
{
	public static void main(String[] args) 
	{
  
		Scanner sc = new Scanner(System.in);
		System.out.println("Shtypni gjatesine e vargut se paku 5: ");
		int gjatesiaVargut = sc.nextInt();
		
		while(gjatesiaVargut < 5)
		{
			System.out.println("Gjatesia e vargut duhet te jete se paku 5 numra: ");
			gjatesiaVargut = sc.nextInt();
		}
		
		int [] vargu = new int[gjatesiaVargut];
		
		for(int i = 0; i<vargu.length;)
		{
			System.out.print("Shtyp numrin e " +(i+1)+ " qe duhet shtypur: " );
			int inputi = sc.nextInt();
			if(inputi >= -10000 && inputi <= 10000)
			{
				vargu[i] = inputi;
				i++;
			}
		}
		double [] rezultati = kalkulo(vargu, gjatesiaVargut);
		System.out.println("Shuma e Djetesheve: " +rezultati[0]);
		System.out.println("Mesatarja e Qindesheve: " +rezultati[1]);
		System.out.println("Perqindja e Mijesheve: " +rezultati[2]);
	}
	
	public static double [] kalkulo(int [] varguMeShenime, int gjatesiaVargut)
	{
		int shumaDhjetsheve = 0;
		int numratoriQindesheve = 0;
		int shumeQindsheve = 0;
		int numratoriMijsheve = 0;
//		double perqindjaNegative = 0;
		
		for(int i = 0; i<varguMeShenime.length; i++)
		{
			if((varguMeShenime[i] >= 10 && varguMeShenime[i] <= 100)||(varguMeShenime[i] >= -100 && varguMeShenime[i] <= -10))
			{
				shumaDhjetsheve+=varguMeShenime[i];
			}
			else if((varguMeShenime[i] >= 100 && varguMeShenime[i] <= 1000)||(varguMeShenime[i] >- 1000 && varguMeShenime[i] <= -100))
			{
				shumeQindsheve+=varguMeShenime[i];
				numratoriQindesheve++;
			}
			else if(varguMeShenime[i] >= 1000 && varguMeShenime[i] <= 10000 || (varguMeShenime[i] >- 10000 && varguMeShenime[i] <= -1000))
			{
				numratoriMijsheve++;
			}	
		}
		return new double[] {shumaDhjetsheve, shumeQindsheve*1.0/numratoriQindesheve, numratoriMijsheve*100*1.0/5};	
	}
}


