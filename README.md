# Comp-5.4
Create a hi low game that asks to replay.
import java.util.Random;
import java.util.Scanner;
public class Comp54 {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        Random generator = new Random();
        int numOfGuess = 0;
        int r = generator.nextInt(100)+1;
        
        System.out.println("Guess the number: ");
        while(true)
        {
            int guess = scan.nextInt();
            if(guess == -1){
                break;
            }
            
            numOfGuess++;
            if(guess < r){
                System.out.println("Guess too low, try again(-1 to quit):'");
            }
            else if(guess > r){
                System.out.println("Guess too high, try again(-1 to quit):");
            }
            else{
                System.out.println("You guess right! You guess within "+numOfGuess+" tries");
                numOfGuess = 0;
                System.out.println("Would you like to play again?(yes/no): ");
                String s = scan.next();
                if(s.equalsIgnoreCase("no")){
                    break;
                }
                else{
                    r = generator.nextInt(100)+1;
                    System.out.println("Please guess the number(-1 to quit): ");
                }
            }
        }
    
    }
    
}
