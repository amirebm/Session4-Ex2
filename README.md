// برنامه ایی بنوسید که تعدادی عدد از ورودی گرفته ،بزرکترین ، کوچکترین و میانگین آن را نشان دهد 



# Session4-Ex2

package com.personal.Ex2;

import java.util.Scanner;

public class Ex2 {

	public static void main(String[] args) {

		int arrayLength;
		Scanner sc= new Scanner(System.in);
		System.out.println("Enter a the size of array");
		arrayLength=sc.nextInt();
		int[] ar= new int[arrayLength];
		
		System.out.println("Please enter "+ arrayLength+ " numbers for array:");
		
		for (int i = 0; i < ar.length; i++) {
		ar[i]=sc.nextInt();	
				
		}
		System.out.println("araye be soorate moratab nashode:");
		
         for (int i = 0; i < ar.length; i++) {
			
			System.out.print( ar[i]+ "\t" );
				
		}
        
         System.out.println();
 		System.out.println("araye be soorate moratab shode:");
 		
 	     quickSort(ar, 0, arrayLength-1);
 	
 	 for (int i = 0; i < arrayLength; i++) {
			
			System.out.print( ar[i]+ "\t" );
				
		}
 	 
		System.out.println();

		System.out.println("kochektarin ozve araye : " + ar[0]);
		System.out.println("bozorgtarin ozve araye : " + ar[arrayLength-1]);
		System.out.println("addade miangin dar araye : " + ar[arrayLength/2]);

        }
	
	static void  quickSort(int ar[], int low, int high) {
		
		int mehvar;
		if(low<high)
		{
			mehvar=parttial(ar, low, high);
			quickSort(ar, low, mehvar-1);
			quickSort(ar, mehvar+1, high);
			
		}
		
		
	}
	
	static int  parttial(int ar[],int low, int high) {
		
		int temp=0;
		int mehvar=ar[low];
		int i=low;
		for (int j =low+1; j <= high; j++) {
			
			if(ar[j]<= mehvar)
			{
			i++;
			temp=ar[j];
			ar[j]=ar[i];
			ar[i]=temp;
			}
		}
		
		temp=ar[i];
		ar[i]=ar[low];
		ar[low]=temp;
		return i;
			
	}

}
