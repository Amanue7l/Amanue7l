- 👋 Hi, I’m @Amanue7lWoldekidan
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Amanue7l/Amanue7l is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import java.util.Scanner;

class Student {
    private int studentId;
    private String name;
    private String type;
    private int age;
    private int year;

    public Student(int studentId, String name, String type, int age, int year) {
        this.studentId = studentId;
        this.name = name;
        this.type = type;
        this.age = age;
        this.year = year;
    }

    // Getters and setters for the class properties go here
    // ...
}

class CampusRegistration {
    private Student[] students;
    private String[] departments;
    private int currentIndex;

    public CampusRegistration(int numStudents) {
        students = new Student[numStudents];
        departments = new String[numStudents];
        currentIndex = 0;
    }

    public void addStudent(int studentId, String name, String type, int age, int year) {
        Student student = new Student(studentId, name, type, age, year);
        students[currentIndex] = student;
    }

    public void addDepartment(int studentId, String department) {
        departments[currentIndex] = department;
        currentIndex++;
    }
}

public class StudentRegistrationApp {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of students to register: ");
        int numStudents = scanner.nextInt();

        CampusRegistration registration = new CampusRegistration(numStudents);
        scanner.nextLine(); // Consume the newline character

        for (int i = 0; i < numStudents; i++) {
            System.out.println("Student #" + (i + 1));

            System.out.print("Enter student type (Undergraduate/Graduate): ");
            String studentType = scanner.nextLine();

            System.out.print("Enter student name: ");
            String name = scanner.nextLine();

            System.out.print("Enter student age: ");
            int age = scanner.nextInt();

            System.out.print("Enter student year: ");
            int year = scanner.nextInt();

            // Add the student to the registration system
            int studentId = i + 1; // You can generate a unique student ID based on your requirements
            registration.addStudent(studentId, name, studentType, age, year);

            scanner.nextLine(); // Consume the newline character

            System.out.print("Enter department for student " + studentId + ": ");
            String department = scanner.nextLine();

            // Add the department for the student
            registration.addDepartment(studentId, department);

            System.out.println("Student #" + (i + 1) + " registered successfully.");
            System.out.println();
        }

        System.out.print("Registration completed. Do you want to continue? (Y/N): ");
        String continueChoice = scanner.nextLine();

        if (continueChoice.equalsIgnoreCase("Y")) {
            // Continue registering more students
            System.out.println("Let's continue with the registration process.");
        } else {
            // Exit the program
            System.out.println("Exiting the program. Thank you!");
            System.exit(0);
        }

        scanner.close();
    }
}


