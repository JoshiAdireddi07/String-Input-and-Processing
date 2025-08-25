# String-Input-and-Processing

    import java.util.Scanner;

    public class StringMethods {
        public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // User input
        System.out.print("Enter your full name (First Last): ");
        String fullName = scanner.nextLine().trim();

        System.out.print("Enter your favorite programming language: ");
        String favLang = scanner.nextLine().trim();

        System.out.print("Enter a sentence about your programming experience: ");
        String sentence = scanner.nextLine().trim();

        // Extract first and last name safely
        String[] nameParts = fullName.split("\\s+"); // handles multiple spaces
        String firstName = nameParts.length > 0 ? nameParts[0] : "";
        String lastName = nameParts.length > 1 ? nameParts[1] : "";

        // Count characters excluding spaces
        int charCount = sentence.replace(" ", "").length();

        // Convert language to uppercase and lowercase
        String langUpper = favLang.toUpperCase();
        String langLower = favLang.toLowerCase();

        // Display summary
        System.out.println("\n--- Summary ---");
        System.out.println("First Name: " + firstName);
        System.out.println("Last Name: " + lastName);
        System.out.println("Favorite Language (UPPER): " + langUpper);
        System.out.println("Favorite Language (lower): " + langLower);
        System.out.println("Sentence character count (no spaces): " + charCount);

        // Extra: check if sentence contains the favorite language
        if (!favLang.isEmpty() && sentence.toLowerCase().contains(favLang.toLowerCase())) {
            System.out.println("Your sentence mentions your favorite language!");
        }

        scanner.close();
    }
}
