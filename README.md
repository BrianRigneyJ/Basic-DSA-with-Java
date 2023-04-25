# Basic DSA with Java

/* This program creates a 2D array of each US state and capital, prompts a user to provide the capital for a random state, then asks the user for the remaining state capitals. Finally, it outputs the number of correct answers. */

import java.security.SecureRandom;
import java.util.Scanner;

public class dsa1 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Initialize the array and load the values
        String [][] states = new String [50][2];
        states [0][0] = "Alabama";
        states [0][1] = "Montgomery";
        states [1][0] = "Alaska";
        states [1][1] = "Junea";
        states [2][0] = "Arizona";
        states [2][1] = "Phoenix";
        states [3][0] = "Arkansas";
        states [3][1] = "Little Rock";
        states [4][0] = "California";
        states [4][1] = "Sacramento";
        states [5][0] = "Colorado";
        states [5][1] = "Denver";
        states [6][0] = "Connecticut";
        states [6][1] = "Hartford";
        states [7][0] = "Delaware";
        states [7][1] = "Dover";
        states [8][0] = "Florida";
        states [8][1] = "Tallahassee";
        states [9][0] = "Georgia";
        states [9][1] = "Atlanta";
        states [10][0] = "Hawaii";
        states [10][1] = "Honolulu";
        states [11][0] = "Idaho";
        states [11][1] = "Boise";
        states [12][0] = "Illinois";
        states [12][1] = "Springfield";
        states [13][0] = "Indiana";
        states [13][1] = "Indianapolis";
        states [14][0] = "Iowa";
        states [14][1] = "Des Moines";
        states [15][0] = "Kansas";
        states [15][1] = "Topeka";
        states [16][0] = "Kentucky";
        states [16][1] = "Frankfort";
        states [17][0] = "Louisiana";
        states [17][1] = "Baton Rouge";
        states [18][0] = "Maine";
        states [18][1] = "Augusta";
        states [19][0] = "Maryland";
        states [19][1] = "Annapolis";
        states [20][0] = "Massachussets";
        states [20][1] = "Boston";
        states [21][0] = "Michigan";
        states [21][1] = "Lansing";
        states [22][0] = "Minnesota";
        states [22][1] = "Saint Paul";
        states [23][0] = "Mississippi";
        states [23][1] = "Jackson";
        states [24][0] = "Missouri";
        states [24][1] = "Jefferson City";
        states [25][0] = "Montana";
        states [25][1] = "Helena";
        states [26][0] = "Nebraska";
        states [26][1] = "Lincoln";
        states [27][0] = "Nevada";
        states [27][1] = "Carson City";
        states [28][0] = "New Hampshire";
        states [28][1] = "Concord";
        states [29][0] = "New Jersey";
        states [29][1] = "Trenton";
        states [30][0] = "New Mexico";
        states [30][1] = "Santa Fe";
        states [31][0] = "New York";
        states [31][1] = "Albany";
        states [32][0] = "North Carolina";
        states [32][1] = "Raleigh";
        states [33][0] = "North Dakota";
        states [33][1] = "Bismarck";
        states [34][0] = "Ohio";
        states [34][1] = "Columbus";
        states [35][0] = "Oklahoma";
        states [35][1] = "Oklahoma City";
        states [36][0] = "Oregon";
        states [36][1] = "Salem";
        states [37][0] = "Pennsylvania";
        states [37][1] = "Harrisburg";
        states [38][0] = "Rhode Island";
        states [38][1] = "Providence";
        states [39][0] = "South Carolina";
        states [39][1] = "Columbia";
        states [40][0] = "South Dakota";
        states [40][1] = "Pierre";
        states [41][0] = "Tennessee";
        states [41][1] = "Nashville";
        states [42][0] = "Texas";
        states [42][1] = "Austin";
        states [43][0] = "Utah";
        states [43][1] = "Salt Lake City";
        states [44][0] = "Vermont";
        states [44][1] = "Montpelier";
        states [45][0] = "Virginia";
        states [45][1] = "Richmond";
        states [46][0] = "Washington";
        states [46][1] = "Olympia";
        states [47][0] = "West Virginia";
        states [47][1] = "Charleston";
        states [48][0] = "Wisconsin";
        states [48][1] = "Madison";
        states [49][0] = "Wyoming";
        states [49][1] = "Cheyenne";
        // Display the contents of the array
        System.out.println("Here are the states with their capitals:");
        for (int r=0; r<50; r++){
            for (int c=0; c<1; c++){
                System.out.print(states[r][0] + ": ");
                System.out.print(states[r][1]);
            }
            System.out.println(); 
        }
        // Generate a random number to ask for a random state capital
        SecureRandom rand = new SecureRandom();
        int int_random = rand.nextInt(50);
        // Ask user for capital of random state
        System.out.println("What is the capital of " + states[int_random][0] + "?");
        String test1resp = scanner.nextLine();
        // Compare user input to correct answer and respond
        if ((test1resp.compareToIgnoreCase(states[int_random][1]) == 0)) {
            System.out.println("That is correct!");
        } else {
            System.out.println("That is incorrect");
        }
        // Re-ordering by capital using a bubble sort
        System.out.println("Now we will reorder by capital name, here are the capitals and their states");
        // Bubble sort
        for (int b = 0; b < 50; b++) {
            for (int a = b + 1; a < 50; a++) {
                // Create temp variables for the reordering
                String capTemp;
                String stateTemp;
                // Compare cities and swap if necessary
                if (states[b][1].compareTo(states[a][1]) > 0) {
                    // Swapping cities and their states
                    capTemp = states[a][1];
                    stateTemp = states[a][0];
                    states[a][1] = states[b][1];
                    states[a][0] = states[b][0];
                    states[b][1] = capTemp;
                    states[b][0] = stateTemp;
                }
            }
        }
        // Outputting the newly sorted array
        for (int r=0; r<50; r++){
            for (int c=0; c<1; c++){
                System.out.print(states[r][1] + ": ");
                System.out.print(states[r][0]);
            }
            System.out.println(); 
        }
        // Now we will ask for all the state capitals
        System.out.println("Now let's really test your knowledge...");
        // Initialize the correct guesses counter
        int correctGuesses = 0;
        // Loop through each state individually and increment the counter if correct
            for (int i = 0; i < 50; i++){
                System.out.println("What is the capital of " + states[i][0] + " ?");
                String guess1 = scanner.nextLine();
                if (guess1.equalsIgnoreCase(states[i][1])){
                correctGuesses++;
                }
            }
        // Finally, output the results 
        if (correctGuesses == 1) {
        System.out.println("You had 1 correct guess!");
        System.out.println("Thank you for playing!");
        } else {
        System.out.println("You had " + correctGuesses + " correct guesses!");
        System.out.println("Thank you for playing!");    
        }   
    }
}
