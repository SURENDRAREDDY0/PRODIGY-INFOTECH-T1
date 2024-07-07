# PRODIGY-INFOTECH-T1
Buid a Temperature Conversion Program
Menu and Input Handling: The main method displays a menu of options for temperature conversion and reads the user's choice using a Scanner.

Conversion Methods: Each conversion option (e.g., Celsius to Fahrenheit) is implemented as a separate static method (celsiusToFahrenheit, celsiusToKelvin, etc.). These methods prompt the user for input, perform the conversion using the respective formulas, and then print the result.
Loop and Exit: The program continues to display the menu until the user chooses to exit (7).

Scanner Usage: Each conversion method creates its own Scanner instance to read user input for temperatures, and then closes the scanner after reading.

//Build a Temperature Conversion Program Using Java :-
// K.SURENDRA REDDY - KARE
import java.util.Scanner;

public class TemperatureConverter {
    public static void main(String[] args) {
        try (Scanner scanner = new Scanner(System.in)) {
            System.out.println("Enter the temperature value: ");
            double temperature = scanner.nextDouble();

            System.out.println("Enter the original unit of measurement (C/F/K): ");
            char unit = scanner.next().toUpperCase().charAt(0);

            switch (unit) {
                case 'C':
                    convertFromCelsius(temperature);
                    break;
                case 'F':
                    convertFromFahrenheit(temperature);
                    break;
                case 'K':
                    convertFromKelvin(temperature);
                    break;
                default:
                    System.out.println("Invalid unit of measurement. Please enter C, F, or K.");
            }
        }
    }

    private static void convertFromCelsius(double celsius) {
        double fahrenheit = celsius * 9 / 5 + 32;
        double kelvin = celsius + 273.15;
        System.out.printf("Celsius: %.2f °C\n", celsius);
        System.out.printf("Fahrenheit: %.2f °F\n", fahrenheit);
        System.out.printf("Kelvin: %.2f K\n", kelvin);
    }

    private static void convertFromFahrenheit(double fahrenheit) {
        double celsius = (fahrenheit - 32) * 5 / 9;
        double kelvin = (fahrenheit + 459.67) * 5 / 9;
        System.out.printf("Fahrenheit: %.2f °F\n", fahrenheit);
        System.out.printf("Celsius: %.2f °C\n", celsius);
        System.out.printf("Kelvin: %.2f K\n", kelvin);
    }

    private static void convertFromKelvin(double kelvin) {
        double celsius = kelvin - 273.15;
        double fahrenheit = kelvin * 9 / 5 - 459.67;
        System.out.printf("Kelvin: %.2f K\n", kelvin);
        System.out.printf("Celsius: %.2f °C\n", celsius);
        System.out.printf("Fahrenheit: %.2f °F\n", fahrenheit);
    }
}
