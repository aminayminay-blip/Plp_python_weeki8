
# Python Toolkit Project
# PLP Week 8 Final Project

# Store shopping items in a list
shopping_list = []

# Keep showing the menu until the user quits
while True:
    print("\n===== MY PYTHON TOOLKIT =====")
    print("1. Greeting Tool")
    print("2. Even or Odd Checker")
    print("3. Shopping List Tool")
    print("4. Quit")

    choice = input("Choose a tool (1-4): ")

    # Tool 1: Greeting
    if choice == "1":
        name = input("What is your name? ")
        print(f"Hello, {name}! Welcome to Python Toolkit.")

    # Tool 2: Even or Odd Checker
    elif choice == "2":
        try:
            number = int(input("Enter a whole number: "))

            if number % 2 == 0:
                print(f"{number} is an even number.")
            else:
                print(f"{number} is an odd number.")

        except ValueError:
            print("Invalid input. Please enter a whole number.")

    # Tool 3: Shopping List
    elif choice == "3":
        while True:
            print("\n--- Shopping List Menu ---")
            print("1. Add an item")
            print("2. View shopping list")
            print("3. Remove an item")
            print("4. Return to main menu")

            action = input("Choose an action (1-4): ")

            if action == "1":
                item = input("Enter an item to add: ").strip()

                if item:
                    shopping_list.append(item)
                    print(f"{item} has been added.")
                else:
                    print("Item cannot be empty.")

            elif action == "2":
                if shopping_list:
                    print("\nYour Shopping List:")
                    for index, item in enumerate(shopping_list, start=1):
                        print(f"{index}. {item}")
                else:
                    print("Your shopping list is empty.")

            elif action == "3":
                if shopping_list:
                    print("Items:", ", ".join(shopping_list))
                    item = input("Enter the item to remove: ").strip()

                    if item in shopping_list:
                        shopping_list.remove(item)
                        print(f"{item} has been removed.")
                    else:
                        print("That item is not in your list.")
                else:
                    print("Your shopping list is empty.")

            elif action == "4":
                break

            else:
                print("Invalid choice. Please select 1-4.")

    # Exit the program
    elif choice == "4":
        print("Thank you for using Python Toolkit. Goodbye!")
        break

    # Handle an invalid menu choice
    else:
        print("Invalid choice. Please select a number from 1 to 4.")
