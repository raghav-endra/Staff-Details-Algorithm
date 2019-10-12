# Staff-Details-Algorithm


import java.util.Scanner;
import java.util.regex.Pattern;
import java.util.*;
class staff
{
	String StaffID,Name,Salary,PhoneNo;
	
	Scanner input = new Scanner(System.in);
void read()
{	
		System.out.println("Enter  staffid ");
		StaffID=input.nextLine();
		while(true)
{
			if(Pattern.matches("[0-9]{5}",StaffID)==false)
			{
				System.out.println(StaffID+" is invalid staffid ,retry");
				StaffID=input.nextLine();
			}
else
				break;
		}
		System.out.println("Enter 10 letter name ");
		Name=input.nextLine();
		while(true)
{
			if(Pattern.matches("[a-zA-Z]{10}",Name)==false){
				System.out.println(Name + "   is invalid name ,retry");
				Name=input.nextLine();}
			else
				break;
		}
		
		System.out.println("Enter salary ");
		Salary=input.nextLine();
		while(true)
{
			if(Pattern.matches("[0-9]{5}",Salary)==false)
{
				System.out.println(Salary+" is invalid salary ,retry");
				Salary=input.nextLine();
}
			else
				break;
		}
		
		System.out.println("Enter Phoneno ");
		PhoneNo=input.nextLine();
		while(true)
{
			if(Pattern.matches("[7-9][0-9]{9}",PhoneNo)==false)
{
				System.out.println(PhoneNo  +" is invalid Phonenumber 
                                           ,retry");
				PhoneNo=input.nextLine();
}
			else
				break;
		}
		
}
			
	void display()
{
		System.out.printf("%-20s","StaffID");
		System.out.printf("%-20s",StaffID);
		System.out.printf("%-20s","Name");
		System.out.printf("%-20s",Name);
		System.out.printf("%-20s","Salary");
		System.out.printf("%-20s",Salary);
		System.out.printf("%-20s","PHONENO");
		System.out.printf("%-20s",PhoneNo);		
	}
	
}

class Teaching extends staff
{
	String Domain,Publication;
	
void read_teaching()
{
		super.read();
		System.out.println("enter domain");
		Domain=input.nextLine();
		while(true)
{
			if(Pattern.matches("[a-zA-Z]{3}",Domain)==false){
			System.out.println(Domain + "   is invalid Domain  ,retry");
			Domain=input.nextLine();
}
		else
			break;
	}
	System.out.println("enter publicatoins");
	Publication=input.nextLine();
	while(true)
{
		if(Pattern.matches("[a-zA-Z]{5}",Publication)==false)
{
			System.out.println(Publication + "   is invalid Publication ,retry");
			Publication=input.nextLine();
}
		else
			break;
	}
}
 
void display()
{
	 super.display();
	 System.out.printf("%-20s","DOMAIN");
	 System.out.printf("%-20s",Domain);
	 System.out.printf("%-20s","PUBLICATIONS");
	 System.out.printf("%-20s",Publication);
 }
}
class Technical extends staff
{
	String skills;
	void read_Technical()
{
		
		super.read();
		System.out.println("enter skills");
		skills=input.nextLine();
		while(true)
{
			if(Pattern.matches("[a-zA-Z]{10}",skills)==false){
			System.out.println(skills + "   is invalid skills ,retry");
			skills=input.nextLine();
}
		else
			break;
	}
}
	

void display()
{
		super.display();
		System.out.printf("%-20s","Skills");
		System.out.printf("%-20s",skills);
}
}	
		
class Contract extends staff
{
	String Period;
	
	void read_contract()
{
		super.read();
		System.out.println("Enter period");
		Period=input.nextLine();
		while(true)
{
			if(Pattern.matches("[1-9]{1}",Period)==false)
{
				System.out.println(Period+ "   is invalid Period ,retry");
				Period=input.nextLine();
}
			else
				break;
		}
}

	void display()
{
		super.display();
		System.out.printf("%-20s","Period");
		System.out.printf("%-20s",Period);
	}
}
public class StaffDetails
 {
	public static void main(String[] args) 
{
		Scanner input= new Scanner(System.in);
		System.out.println("Enter the number of staff details to be created");
		int n=input.nextInt();
		Teaching steach[]=new Teaching[n];
		Technical stech[]=new Technical[n];
		Contract scon[]=new Contract[n];



		for(int i=0;i<n;i++)
{
			System.out.println("Enter teaching staff details");
			steach[i]=new Teaching();
			steach[i].read_teaching();
				
		}
			
		for(int i=0;i<n;i++)
{
			System.out.println("Enter technical staff details");
			stech[i]=new Technical();
			stech[i].read_Technical();
		}
			
for(int i=0;i<n;i++)
{
			System.out.println("Enter contract staff details");
			scon[i]=new Contract();									
      scon[i].read_contract();
		}
			
		System.out.println("\nstaff details:\n");
		System.out.println("-------Teaching staff details----------");
		for(int i=0;i<n;i++)
{
			steach[i].display();
		}
			 
		System.out.println();
		System.out.println("---------Technical staff details-------");					
    for(int i=0;i<n;i++)
{
	stech[i].display();
		}
		System.out.println();
		System.out.println("---------Contract staff details--------");
				
		for(int i=0;i<n;i++)
{
				scon[i].display();
		}
		input.close();
	}

}
