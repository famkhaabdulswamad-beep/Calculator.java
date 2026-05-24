 java.util.Scanner;

public class Calculator {
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean continueCalculating = true;
        
        while (continueCalculating) {
            System.out.println("\n=== Simple Calculator ===");
            System.out.println("1. Addition");
            System.out.println("2. Subtraction");
            System.out.println("3. Multiplication");
            System.out.println("4. Division");
            System.out.println("5. Exit");
            System.out.print("Choose an operation (1-5): ");
            
            int choice = scanner.nextInt();
            
            if (choice == 5) {
                System.out.println("Thank you for using the calculator!");
                continueCalculating = false;
                break;
            }
            
            if (choice < 1 || choice > 5) {
                System.out.println("Invalid choice! Please select a valid operation.");
                continue;
            }
            
            System.out.print("Enter first number: ");
            double num1 = scanner.nextDouble();
            
            System.out.print("Enter second number: ");
            double num2 = scanner.nextDouble();
            
            double result = 0;
            boolean validOperation = true;
            
            switch (choice) {
                case 1:
                    result = add(num1, num2);
                    System.out.println("Result: " + num1 + " + " + num2 + " = " + result);
                    break;
                case 2:
                    result = subtract(num1, num2);
                    System.out.println("Result: " + num1 + " - " + num2 + " = " + result);
                    break;
                case 3:
                    result = multiply(num1, num2);
                    System.out.println("Result: " + num1 + " * " + num2 + " = " + result);
                    break;
                case 4:
                    if (num2 == 0) {
                        System.out.println("Error: Cannot divide by zero!");
                        validOperation = false;
                    } else {
                        result = divide(num1, num2);
                        System.out.println("Result: " + num1 + " / " + num2 + " = " + result);
                    }
                    break;
            }
        }
        
        scanner.close();
    }
    
    // Addition method
    public static double add(double a, double b) {
        return a + b;
    }
    
    // Subtraction method
    public static double subtract(double a, double b) {
        return a - b;
    }
    
    // Multiplication method
    public static double multiply(double a, double b) {
        return a * b;
    }
    
    // Division method
    public static double divide(double a, double b) {
        return a / b;
    }
}
