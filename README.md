# Dart-Assignment
Data Types &amp; Control Flow

// --- Data Types Implementation ---

void demonstrateDataTypes() {
  print("--- Data Types Implementation ---");

  // Define Variables
  int age = 30;
  double price = 19.99;
  String name = "Alice";
  bool isActive = true;
  List<int> primeNumbers = [2, 3, 5, 7, 11];

  print("Integer (age): $age");
  print("Double (price): $price");
  print("String (name): $name");
  print("Boolean (isActive): $isActive");
  print("List of Integers (primeNumbers): $primeNumbers");

  print("\n--- Type Conversion ---");

  // Type Conversion (within the same function for simplicity)
  String numberAsString = "123";
  String doubleAsString = "45.67";
  int intValue = 42;
  double doubleValue = 98.76;

  // Convert String to int and double
  try {
    int stringToInt = int.parse(numberAsString);
    double stringToDouble = double.parse(doubleAsString);
    print("Converted String '$numberAsString' to int: $stringToInt");
    print("Converted String '$doubleAsString' to double: $stringToDouble");
  } catch (e) {
    print("Error during String to number conversion: $e");
  }

  // Convert int to String and double
  String intToString = intValue.toString();
  double intToDouble = intValue.toDouble();
  print("Converted int $intValue to String: '$intToString'");
  print("Converted int $intValue to double: $intToDouble");

  // Convert double to String
  String doubleToString = doubleValue.toString();
  print("Converted double $doubleValue to String: '$doubleToString'");

  print("\n--- Function for Conversion ---");
  convertAndDisplay("789");
  convertAndDisplay("10.5");
  convertAndDisplay("abc"); // Example of invalid input
}

// Function for Conversion
void convertAndDisplay(String inputString) {
  print("Attempting to convert and display: '$inputString'");
  try {
    int convertedToInt = int.parse(inputString);
    print("  Converted to int: $convertedToInt");
  } catch (e) {
    print("  Could not convert '$inputString' to int: Invalid format.");
  }

  try {
    double convertedToDouble = double.parse(inputString);
    print("  Converted to double: $convertedToDouble");
  } catch (e) {
    print("  Could not convert '$inputString' to double: Invalid format.");
  }
}

// --- Control Flow ---

void demonstrateControlFlow() {
  print("\n--- Control Flow ---");

  // If-Else Statements (Positive, Negative, Zero)
  print("\n--- If-Else (Positive, Negative, Zero) ---");
  checkNumberSign(10);
  checkNumberSign(-5);
  checkNumberSign(0);

  // If-Else Statements (Voting Eligibility)
  print("\n--- If-Else (Voting Eligibility) ---");
  checkVotingEligibility(20);
  checkVotingEligibility(18);
  checkVotingEligibility(16);

  // Switch Case (Day of the week)
  print("\n--- Switch Case (Day of the week) ---");
  printDayOfWeek(1);
  printDayOfWeek(4);
  printDayOfWeek(7);
  printDayOfWeek(9); // Invalid day

  // Loops
  print("\n--- Loops ---");

  // For loop (1 to 10)
  print("\n--- For loop (1 to 10) ---");
  for (int i = 1; i <= 10; i++) {
    print(i);
  }

  // While loop (10 to 1)
  print("\n--- While loop (10 to 1) ---");
  int j = 10;
  while (j >= 1) {
    print(j);
    j--;
  }

  // Do-While loop (1 to 5)
  print("\n--- Do-While loop (1 to 5) ---");
  int k = 1;
  do {
    print(k);
    k++;
  } while (k <= 5);
}

// Helper function for checking number sign
void checkNumberSign(int number) {
  if (number > 0) {
    print("$number is positive.");
  } else if (number < 0) {
    print("$number is negative.");
  } else {
    print("$number is zero.");
  }
}

// Helper function for checking voting eligibility
void checkVotingEligibility(int age) {
  if (age >= 18) {
    print("Age $age: Eligible to vote.");
  } else {
    print("Age $age: Not eligible to vote.");
  }
}

// Helper function for printing day of the week
void printDayOfWeek(int dayNumber) {
  switch (dayNumber) {
    case 1:
      print("Day $dayNumber: Monday");
      break;
    case 2:
      print("Day $dayNumber: Tuesday");
      break;
    case 3:
      print("Day $dayNumber: Wednesday");
      break;
    case 4:
      print("Day $dayNumber: Thursday");
      break;
    case 5:
      print("Day $dayNumber: Friday");
      break;
    case 6:
      print("Day $dayNumber: Saturday");
      break;
    case 7:
      print("Day $dayNumber: Sunday");
      break;
    default:
      print("Day $dayNumber: Invalid day number.");
  }
}

// --- Combining Data Types and Control Flow ---

void demonstrateCombinedConcepts() {
  print("\n--- Combining Data Types and Control Flow ---");

  // Define a List of int numbers
  List<int> numbers = [15, 8, 27, 4, 5, 100, 3, 250, 105, 1, 10, 11, 101, 55];

  // Use a for loop to iterate through the list
  for (int number in numbers) {
    // Print each number
    print("Processing number: $number");

    // Use if-else statements to check if the number is even or odd
    if (number % 2 == 0) {
      print("  This number is even.");
    } else {
      print("  This number is odd.");
    }

    // Implements a switch statement to categorize numbers
    // Using if-else if to determine the category for ranges.
    String category;
    if (number >= 1 && number <= 10) {
      category = "small";
    } else if (number >= 11 && number <= 100) {
      category = "medium";
    } else if (number >= 101) {
      category = "large";
    } else {
      category = "other"; // For numbers outside the defined ranges (e.g., 0 or negative)
    }

    // Now use the switch statement on the calculated category
    switch (category) {
      case "small":
        print("  Category: Small");
        break;
      case "medium":
        print("  Category: Medium");
        break;
      case "large":
        print("  Category: Large");
        break;
      default:
        print("  Category: Unknown or outside defined ranges");
    }
    print("-" * 20); // Separator for clarity
  }
}

// --- Main Function to run all demonstrations ---

void main() {
  demonstrateDataTypes();
  demonstrateControlFlow();
  demonstrateCombinedConcepts();
}
