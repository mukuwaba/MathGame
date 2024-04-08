import java.security.SecureRandom; // Importing SecureRandom class for generating random numbers
import java.util.Scanner; // Importing Scanner class for user input

public class MathGame {

    public static void main(String[] args) {
        SecureRandom random = new SecureRandom(); // Creating a SecureRandom object for generating random numbers
        Scanner scanner = new Scanner(System.in); // Creating a Scanner object for user input
        int score = 0; // Initializing the score variable to keep track of the user's score

        // Loop for asking 10 questions
        for (int i = 1; i <= 10; i++) {
            int num1 = random.nextInt(9) + 1; // Generates a random number between 1 and 9 for the first operand
            int num2 = random.nextInt(9) + 1; // Generates a random number between 1 and 9 for the second operand
            int correctAnswer = num1 * num2; // Calculates the correct answer for the question

            // Prompting the user with the question
            System.out.printf("Question %d: How much is %d x %d?\n", i, num1, num2);

            // Loop until the user provides the correct answer
            while (true) { //(true)= condition of while loop
                System.out.print("Enter your answer: ");
                int userAnswer = scanner.nextInt(); // Reading the user's answer from the console

                // Checking if the user's answer is correct
                if (userAnswer == correctAnswer) { //(user...) sets break out condition
                    System.out.println("Good job! Well done!"); // Printing a success message if the answer is correct
                    score++; // Increment the score by 1 for a correct answer
                    break; // Break out of the loop if the answer is correct
                } //END: if

                else {
                    System.out.println("Try again!"); // Printing a failure message if the answer is incorrect
                    score--; // Decrement the score by 1 for an incorrect answer
                }//END: else
            }//END: while
        }//END: for

        // Display score report
        System.out.printf("You scored %d out of 10!\n", score);
    }
}
