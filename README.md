import java.util.ArrayList;
import java.util.Scanner;

public class GradeCalculator {

    public static void main(String[] args) {
        ArrayList<Integer> grades = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter student grades (type -1 to end):");
        
        // Collect grades from the user
        while (true) {
            System.out.print("Enter grade: ");
            int grade = scanner.nextInt();
            if (grade == -1) break;  // Stop entering grades if user types -1
            grades.add(grade);
        }

        if (grades.isEmpty()) {
            System.out.println("No grades were entered.");
        } else {
            // Compute average, highest, and lowest grades
            int highest = grades.get(0);
            int lowest = grades.get(0);
            int sum = 0;

            for (int grade : grades) {
                sum += grade;
                if (grade > highest) highest = grade;
                if (grade < lowest) lowest = grade;
            }

            double average = (double) sum / grades.size();

            // Display results
            System.out.println("Average grade: " + average);
            System.out.println("Highest grade: " + highest);
            System.out.println("Lowest grade: " + lowest);
        }
        
        scanner.close();
    }
}
