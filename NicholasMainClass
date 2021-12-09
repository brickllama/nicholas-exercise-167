//AUTHOR: Nathaniel Nicholas
//COURSE: CPT167
//PURPOSE: To provide the user with a menu based shopping service, providing: prices, discounts, quantity, taxes, and totals.
//CREATEDATE: 12/7/2021

package edu.cpt167.nicholas.exercise6;

//open scanner
import java.util.Scanner;

public class NicholasMainClass
{
	// declare and initialize all class constants
	public static final double TAX_RATE = .075;
	public static final String DISCOUNT_NAME_MEMBER = "Member";
	public static final String DISCOUNT_NAME_SENIOR = "Senior";
	public static final String DISCOUNT_NAME_NONE = "No Discount";
	public static final String DISCOUNT_NAME_QUIT = "Quit";
	public static final double DISCOUNT_RATE_MEMBER = .15;
	public static final double DISCOUNT_RATE_SENIOR = .25;
	public static final double DISCOUNT_RATE_NONE = 0.0;
	public static final String ITEM_NAME_PREMIUM = "Sony Headphones";
	public static final String ITEM_NAME_SPECIAL = "Skullcandy Headphones";
	public static final String ITEM_NAME_BASIC = "JLab Earbuds";
	public static final String ITEM_NAME_RETURN = "Return to Main Menu";
	public static final double ITEM_PRICE_PREMIUM = 55.95;
	public static final double ITEM_PRICE_SPECIAL = 24.95;
	public static final double ITEM_PRICE_BASIC = 15.95;
	public static final int RESET_VALUE = 0;

	// main method
	public static void main(String[] args)
	{
		// introduction section
		// declare and initialize the Scanner
		Scanner input = new Scanner(System.in);

		// declare and initialize all local variables
		String userName = "";
		char rateSelection = ' ';
		char itemSelection = ' ';
		int howMany = 0;
		String discountName = "";
		double discountRate = 0;
		String itemName = "";
		double itemPrice = 0;
		double discountAmount = 0;
		double discountPrice = 0;
		double subTotal = 0;
		double tax = 0;
		double totalCost = 0;
		int memberCount = 0;
		int seniorCount = 0;
		int noDiscountCount = 0;
		double grandTotal = 0;
		int premiumCount = 0;
		int specialCount = 0;
		int basicCount = 0;
		double purchaseAmt = 0;

		// display the welcome banner
		displayWelcomeBanner();

		// input section

		// prompts the user for their name
		userName = getUserName(input);

		// prime read
		rateSelection = validateMainMenu(input);

		// repetition structure

		// 'run-while' not quit loop
		while (rateSelection != 'Q')
		{
			// assignment statement to assign a valid item selection
			itemSelection = validateItemMenu(input);

			// run-while itemSelection !='R'
			while (itemSelection != 'R')
			{
				howMany = validateHowMany(input);

				// process section

				// process selection structure
				// test to see which combo name and price to assign
				if (rateSelection == 'A')
				{
					// assignment statement
					discountName = DISCOUNT_NAME_MEMBER;
					discountRate = DISCOUNT_RATE_MEMBER;
					memberCount++;
				} // end of if
				else if (rateSelection == 'B')
				{
					// assignment statement
					discountName = DISCOUNT_NAME_SENIOR;
					discountRate = DISCOUNT_RATE_SENIOR;
					seniorCount++;
				} // end of else if
				else
				{
					// assignment statement
					discountName = DISCOUNT_NAME_NONE;
					discountRate = DISCOUNT_RATE_NONE;
					noDiscountCount++;
				} // end of else

				// process selection structure
				// test to see which item name and price to assign

				if (itemSelection == 'A')
				{
					// assignment statement
					itemName = ITEM_NAME_PREMIUM;
					itemPrice = ITEM_PRICE_PREMIUM;
					premiumCount++;
				} // end of if
				else if (itemSelection == 'B')
				{
					// assignment statement
					itemName = ITEM_NAME_SPECIAL;
					itemPrice = ITEM_PRICE_SPECIAL;
					specialCount++;
				} // end of else if
				else
				{
					// assignment statement
					itemName = ITEM_NAME_BASIC;
					itemPrice = ITEM_PRICE_BASIC;
					basicCount++;
				} // end of else

				// assignment statement for the totals
				discountAmount = itemPrice * discountRate;
				discountPrice = itemPrice - discountAmount;
				purchaseAmt = howMany * discountPrice;
				subTotal = subTotal + purchaseAmt;

				// output section

				displayItemReceipt(itemName, itemPrice, discountName, discountRate, discountAmount, discountPrice,
						howMany, purchaseAmt, subTotal);

				// duplicate itemSelection
				itemSelection = validateItemMenu(input);
			} // end of run-while itemSelection != 'R'
				// user selects 'R' we print an order total vs item receipt and go up to main
				// menu
				// assignment statement for the totals
			tax = subTotal * TAX_RATE;
			totalCost = subTotal + tax;
			grandTotal = grandTotal + totalCost;
			displayOrderTotal(userName, subTotal, tax, totalCost);
			subTotal = RESET_VALUE;
			rateSelection = validateMainMenu(input);
		} // end of run-while rateSelection = 'Q'

		// display final report if items purchased
		if (grandTotal > 0.0)
		{
			displayFinalReport(memberCount, seniorCount, noDiscountCount, premiumCount, specialCount, basicCount,
					grandTotal);
		}

		// display the farewell message
		displayFarewellMessage();

		// close scanner
		input.close();
	}// end of main method

	// void method section

	// void method to display the welcome banner
	public static void displayWelcomeBanner()
	{
		System.out.println("Welcome to the Headphone Program");
		System.out.println("This program will allow you to purchase headphones");
		System.out.println("and will report the cost of your purchase");
		// border
		System.out.println("***** ***** ***** ***** ***** ***** ***** ***** ****** *****");
	}// end of void method to display the welcome banner

	// void method to display the farewell message
	public static void displayFarewellMessage()
	{
		// display the farewell message
		System.out.println("\nThank you for using the Headphone Program!");
		System.out.println("Have a nice day!");
	}// end of void method to display the welcome banner

	// void method to display the item receipt
	public static void displayItemReceipt(String borrowedItemName, double borrowedItemPrice,
			String borrowedDiscountName, double borrowedDiscountRate, double borrowedDiscountAmount,
			double borrowedDiscountPrice, int borrowedHowMany, double borrowedPurchaseAmt, double borrowedSubTotal)
	{
		// item report
		System.out.println("\n~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// title
		System.out.println("ITEM REPORT");
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// item report details
		System.out.printf("%-17s%s\n", "Item name ", borrowedItemName);
		System.out.printf("%-17s%-2s%10.2f\n", "Original Price", "$", borrowedItemPrice);
		System.out.printf("%-17s%s\n", "Discount Type", borrowedDiscountName);
		System.out.printf("%-17s%11.1f %%\n", "Discount Rate", borrowedDiscountRate * 100);
		System.out.printf("%-17s%-2s%10.2f\n", "Discount Amount", "$", borrowedDiscountAmount);
		System.out.printf("%-17s%-2s%10.2f\n", "Discounted Price ", "$", borrowedDiscountPrice);
		System.out.printf("%-17s%12d\n", "Quantity ", borrowedHowMany);
		System.out.printf("%-17s%-2s%10.2f\n", "Subtotal ", "$", borrowedPurchaseAmt);
		System.out.printf("%-17s%-2s%10.2f\n", "Tax ", "$", borrowedSubTotal);
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
	}// end of void method to display the item receipt

	// void method to display the order total
	public static void displayOrderTotal(String borrowedUserName, double borrowedSubTotal, double borrowedTax,
			double borrowedTotalCost)
	{
		// order total
		System.out.println("\n~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// title
		System.out.println("ORDER REPORT");
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// order report details
		System.out.printf("%-17s%s\n", "User  ", borrowedUserName);
		System.out.printf("%-17s%-2s%10.2f\n", "Subtotal", "$", borrowedSubTotal);
		System.out.printf("%-17s%-2s%10.2f\n", "Tax", "$", borrowedTax);
		System.out.printf("%-17s%-2s%10.2f\n", "Total Cost", "$", borrowedTotalCost);
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
	}// end of void method to display the order total

	// void method to display the final report
	public static void displayFinalReport(int borrowedMemberCount, int borrowedSeniorCount, int borrowedNoDiscountCount,
			int borrowedPremiumCount, int borrowedSpecialCount, int borrowedBasicCount, double borrowedGrandTotal)
	{
		// report
		System.out.println("\n~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// report title
		System.out.println("FINAL REPORT");
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// report details
		System.out.println("Count of discount types:");
		System.out.printf("%-26s %d\n", DISCOUNT_NAME_MEMBER, borrowedMemberCount);
		System.out.printf("%-26s %d\n", DISCOUNT_NAME_SENIOR, borrowedSeniorCount);
		System.out.printf("%-26s %d\n", DISCOUNT_NAME_NONE, borrowedNoDiscountCount);
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		System.out.println("Count of item types:");
		System.out.printf("%-26s %d\n", ITEM_NAME_PREMIUM, borrowedPremiumCount);
		System.out.printf("%-26s %d\n", ITEM_NAME_SPECIAL, borrowedSpecialCount);
		System.out.printf("%-26s %d\n", ITEM_NAME_BASIC, borrowedBasicCount);
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		System.out.printf("%-17s$%10.2f\n", "Grand Total", borrowedGrandTotal);
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
	}// end of void method to display the final report

	// void method to display the main menu
	public static void displayMainMenu()
	{

		// menu
		System.out.println("\n~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// menu title
		System.out.println("DISCOUNT MENU");
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// menu options
		System.out.printf("|A| for %-15s%5.1f%%\n", DISCOUNT_NAME_MEMBER, DISCOUNT_RATE_MEMBER * 100);
		System.out.printf("|B| for %-15s%5.1f%%\n", DISCOUNT_NAME_SENIOR, DISCOUNT_RATE_SENIOR * 100);
		System.out.printf("|C| for %-15s%5.1f%%\n", DISCOUNT_NAME_NONE, DISCOUNT_RATE_NONE * 100);
		System.out.printf("|Q| to %s\n", DISCOUNT_NAME_QUIT);
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");

		// menu prompt
		System.out.print("Enter your selection here: ");
	}// end of void method to display the main menu

	// void method to display the item menu
	public static void displayItemMenu()
	{
		// menu
		System.out.println("\n~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// menu title
		System.out.println("ITEM MENU");
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");
		// menu options
		System.out.printf("|A| for %-25s$%5.2f\n", ITEM_NAME_PREMIUM, ITEM_PRICE_PREMIUM);
		System.out.printf("|B| for %-25s$%5.2f\n", ITEM_NAME_SPECIAL, ITEM_PRICE_SPECIAL);
		System.out.printf("|C| for %-25s$%5.2f\n", ITEM_NAME_BASIC, ITEM_PRICE_BASIC);
		System.out.printf("|R| to %-25s\n", ITEM_NAME_RETURN);
		System.out.println("~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~ ~~~~");

		// menu prompt
		System.out.print("Enter your selection here: ");
	}// end of void method to display the item menu

	// VR method to validate userName
	public static String getUserName(Scanner borrowedInput)
	{
		// declare and initialize local variables
		String localUserName = "";
		// prompts the user for their name
		System.out.print("Please enter your first name: ");
		// assignment statement
		localUserName = borrowedInput.nextLine();

		return localUserName;
	}// end of validation method for userName

	// VR method to display the main menu
	public static char validateMainMenu(Scanner borrowedInput)
	{
		// declare and initialize local variable
		char localRateSelection = ' ';

		displayMainMenu();

		// assignment statement
		localRateSelection = borrowedInput.next().toUpperCase().charAt(0);

		// repetition structure
		// validation loop for discount selection
		while (localRateSelection != 'A' && localRateSelection != 'B' && localRateSelection != 'C'
				&& localRateSelection != 'Q')
		{
			// simple error message
			System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
			System.out.println("The selection made is invalid. Please try again.");
			System.out.println("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");

			displayMainMenu();

			// assignment statement
			localRateSelection = borrowedInput.next().toUpperCase().charAt(0);
		} // END of validation loop - for rate selection
		return localRateSelection;
	}// end of validation method to display the main menu

	// VR method to display the item menu
	public static char validateItemMenu(Scanner borrowedInput)
	{
		// declare and initialize local variable
		char localItemSelection = ' ';

		displayItemMenu();

		// assignment statement
		localItemSelection = borrowedInput.next().toUpperCase().charAt(0);

		// repetition structure
		// validation loop for item selection
		while (localItemSelection != 'A' && localItemSelection != 'B' && localItemSelection != 'C'
				&& localItemSelection != 'R')
		{
			// simple error message
			System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
			System.out.println("The selection made is invalid. Please try again.");
			System.out.println("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");

			displayItemMenu();

			// assignment statement
			localItemSelection = borrowedInput.next().toUpperCase().charAt(0);
		} // end of validation loop for item menu
		return localItemSelection;
	}// end of validation to display the item menu

	// VR method to validate how many
	public static int validateHowMany(Scanner borrowedInput)
	{
		// declare and initialize variable
		int localHowMany = 0;

		// prompt user for input
		System.out.print("Quantity: ");
		localHowMany = borrowedInput.nextInt();

		while (localHowMany <= 0)
		{
			// simple error message
			System.out.println("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
			System.out.println("The value entered is invalid. Please try again.");
			System.out.println("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
			System.out.print("Quantity: ");
			localHowMany = borrowedInput.nextInt();
		}
		return localHowMany;
	}// end of validation method to validate how many

} // end of main class
