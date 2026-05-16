    import java.util.Scanner;
    
    public class MoodTracker {

    
    public static void giveAdvice(String mood) {

        if (mood.equalsIgnoreCase("happy")) {
            System.out.println("Keep smiling and enjoy your day! 😊");
        }

        else if (mood.equalsIgnoreCase("sad")) {
            System.out.println("Try listening to music or talking to a friend 🎧");
        }

        else if (mood.equalsIgnoreCase("stressed")) {
            System.out.println("Take a short break and relax 🌿");
        }

        else if (mood.equalsIgnoreCase("angry")) {
            System.out.println("Take deep breaths and stay calm 😌");
        }

        else if (mood.equalsIgnoreCase("tired")) {
            System.out.println("Get some rest and drink water 💧");
        }

        else {
            System.out.println("Have a nice day 💜");
        }
    }

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        
        String[] moods = new String[10];

        int count = 0;
        int choice = 0;

        System.out.println("=================================");
        System.out.println(" Welcome to Mood Tracker System ");
        System.out.println("=================================");

       
        while (choice != 4) {

            System.out.println("\nMenu:");
            System.out.println("1- Add Mood");
            System.out.println("2- View Moods");
            System.out.println("3- Get Advice");
            System.out.println("4- Exit");

            System.out.print("Choose an option: ");
            choice = input.nextInt();
            input.nextLine();

            switch (choice) {

                
                case 1:

                    if (count < moods.length) {

                        System.out.print("Enter your mood: ");
                        String mood = input.nextLine();

                        moods[count] = mood;
                        count++;

                        System.out.println("Mood saved successfully! ✅");
                    }

                    else {
                        System.out.println("Mood list is full!");
                    }

                    break;

                
                case 2:

                    if (count == 0) {
                        System.out.println("No moods saved yet.");
                    }

                    else {

                        System.out.println("\nYour Saved Moods:");

                        for (int i = 0; i < count; i++) {
                            System.out.println((i + 1) + "- " + moods[i]);
                        }
                    }

                    break;

               
                case 3:

                    System.out.print("Enter your mood to get advice: ");
                    String userMood = input.nextLine();

                    System.out.println("\nAdvice:");
                    giveAdvice(userMood);

                    break;

               
                case 4:

                    System.out.println("Thank you for using Mood Tracker 💜");
                    break;

               
                default:

                    System.out.println("Invalid choice. Try again.");
            }
        }

        input.close();
    }
    
    }
