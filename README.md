REG N:225064914
JAVA LAB ACTIVITY:
1. Program 1: BicycleRental


Description

This program prompts the user for a start hour and an end hour (24-hour format), validates the input bounds, and iterates through each hour to calculate the total rental fee in RWF (Rwandan Francs).

Block & Line Breakdown

• BLOCK 1 (Lines 2–4 & Line 31)
	• Code: Scanner input = new Scanner(System.in); and input.close();
	• Function: Initializes the input stream from the console and safely closes the resource at the end of the program to prevent memory leaks.
• BLOCK 2 (Lines 5–8)
	• Code: System.out.print(...) with input.nextInt() for startTime and endTime.
	• Function: Displays prompts asking the user to enter the starting hour (0–23) and ending hour (1–24), and reads the integer values into memory.
• BLOCK 3 (Lines 9–17)
	• Code: if (startTime < 0 || ...) and if (startTime >= endTime)
	• Function: Performs input validation checks:
		• Ensures startTime is between 0 and 23 and endTime is between 1 and 24.
		• Ensures the starting time is strictly less than the ending time. If invalid, it prints an error message and terminates the program early (return).
• BLOCK 4 (Lines 18–30)
	• Code: for (int hour = startTime; hour < endTime; hour++) { ... } and System.out.println("Total rental cost: " + totalRent + " RWF");
	• Function: Loops through each hour of the rental duration and applies tiered pricing:
		• 0500 RWF / hour: Hours from 0–6 (12:00 AM – 6:59 AM) or 21–23 (9:00 PM – 11:59 PM).
		• 1000 RWF / hour: Hours from 7–13 (7:00 AM – 1:59 PM) or 19–20 (7:00 PM – 8:59 PM).
		• 1500 RWF / hour: Hours from 14–18 (2:00 PM – 6:59 PM).
		• Finally, it prints the accumulated totalRent in RWF.

 Program 2: MushroomIdentifier


Description

An interactive terminal classification tool that asks the user a sequence of yes/no questions about physical characteristics (gills, forest habitat, ring, convex cup) to match an input mushroom to a specific species name.

Block & Line Breakdown

• Setup & Initialization (Lines 2–5)
	• Code: Scanner input = new Scanner(System.in);
	• Function: Sets up the Scanner object to read keyboard input strings.
• LINE 1 & LINE 2 (Lines 6–8)
	• Code: System.out.println("--- Mushroom Identifier ---"); and System.out.print("Does your mushroom have gills? (yes/no): ");
	• Function: Prints the title header and asks the first primary question (gills), standardizing the input to lowercase and trimming whitespace (trim().toLowerCase()).
• LINE 3 (Lines 9–11)
	• Code: if (gills.equals("no")) { System.out.println("\nYour mushroom is: Cepe de bordeau"); }
	• Function: If the mushroom does not have gills, it immediately classifies it as Cepe de bordeau.
• LINE 4 (Lines 12–16)
	• Code: else { System.out.print("Does your mushroom grow in a forest? (yes/no): ...);
	• Function: If the mushroom has gills, it triggers the else branch and asks a secondary question: does it grow in a forest?
• BLOCK 5 (Lines 17–33)
	• Code: Nested if-else branches (forest.equals("yes") vs no)
	• Function: Deepens the decision tree:
		• If it grows in a forest (yes): Asks if it has a ring.
			• Ring = yes → Outputs Amanite tue-mouche
			• Ring = no → Outputs Pied bleu
		• If it does not grow in a forest (no): Asks if it has a convex cup.
			• Convex cup = yes → Outputs Agaric jaunissant
			• Convex cup = no → Outputs Coprin chevelu
• Cleanup (Line 34)
	input.close();:
	Function: Closes the Scanner stream.
