# Shunem
package com.manipulatingArrays;

import java.util.*;
import java.util.stream.Collectors;

public class ManipulatingArrays {
    static void myArray(int a[]) {
    	
    	int max=Arrays.stream(a).max().getAsInt();
    	System.out.println("This is the maximum number "+max+"\n");
    	
    	int secondMaxEven=Arrays.stream(a)
    			.boxed()
    			.filter(n->n%2==0)
    			.sorted(Comparator.reverseOrder())
    			.skip(1)
    			.findFirst().get();
		System.out.println("This the second maximum even number "+secondMaxEven+"\n");
		
    	if(max%2==0) {
    		
    		List<Integer> myNewList=Arrays
    				.stream(a)
    				.boxed().filter(n->n%2!=0).collect(Collectors.toList());
    				int minOddNumber=Collections.min(myNewList);    						
    				System.out.println("This is the minimum odd number "+minOddNumber+"\n");
    				
    				if(minOddNumber>secondMaxEven)
    					System.out.print("This is the minimum odd number that is greater than all even values "+minOddNumber);
    				
    			
    		}
    	}
        
    
	public static void main(String[] args) {
		// TODO Auto-generated method stub
       int a[]= {11, 4, 20, 9, 2, 8};
		myArray(a);
		
	}

}
