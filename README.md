# Coding-Projects
This contains my coding projects that I've done
/*Purpose: To create an array of names and be able to withdraw 
 * the first, middle, last names and the initials, returning the 
 * lengths of the names, as well as the length of the full name. 
 * The program should also print out a random sequence of 5 letters from the current name.(Program1Initials)
 * Insight: The reason for the argument for the call random.nextInt(currentName.length()-4)
 * is -4 and not 4 is because the nextInt has to -4 after the length
 * in order to so that the random sequence of letters stops after 5 letters.
 * Otherwise the substring might be too small and won't take the random 5
 * letters before the end of the last name.
 */
package initials;

import java.util.Random;

public class Program1Initials {

	public static void main(String[] args) {
		String[] strings = { "David Lee Alger", "Kate Garry Hudson", "Tina Stamatina Fey", "Hugh Mungo Grant",
		"Uma Karuna Thurman" };
		
		Random random = new Random();
		
		for (int i = 0; i < strings.length; i++) {
			//variables for the incoming names in each item of the array
			String currentName = strings[i];
			int firstSpace = currentName.indexOf(" ");
			int secondSpace = currentName.indexOf(" ", firstSpace + 1);
			String firstName = currentName.substring(0, firstSpace);
			String middleName = currentName.substring(firstSpace+1, secondSpace);
			String lastName = currentName.substring(secondSpace+1);
			int randomNumber = random.nextInt(currentName.length()-4);
			
			//printing first, middle, last name
			System.out.println("Your first name is "+
					firstName+" with a length of "+
					firstName.length());
			System.out.println("Your middle name is "+
					middleName+" with a length of "+
					middleName.length());
			System.out.println("Your last name is "+
					lastName+" with a length of "+
					lastName.length());
			System.out.println("Your initials are "+
					firstName.charAt(0)+
					middleName.charAt(0)+
					lastName.charAt(0)+
					". The length of your entire name is "+
					currentName.length());
			
			//print random sequence of 5 letters
			System.out.println("A random sequence of 5 letters in your name is "
					+"\""+currentName.substring(randomNumber, randomNumber+5)+"\"");
			System.out.println();
			System.out.println();
		}
	}
}
