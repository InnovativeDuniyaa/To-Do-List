# To-Do-List
Python Made Easy: Build Your Own To-Do List
todo_list = []

def add_task(task):
    todo_list.append(task)
    print(f"Task '{task}' has been added to your to-do list.")

def view_tasks():
    if not todo_list:
        print("Your to-do list is empty.")
    else:
        print("Your To-Do List:")
        for i, task in enumerate(todo_list, start=1):
            print(f"{i}. {task}")

def complete_task(index):
    if 1 <= index <= len(todo_list):
        completed_task = todo_list.pop(index - 1)
        print(f"Task '{completed_task}' has been marked as completed and removed from your to-do list.")
    else:
        print("Invalid task index. Please enter a valid index.")

while True:
    print("\nTo-Do List Menu:")
    print("1. Add a task")
    print("2. View tasks")
    print("3. Mark a task as completed")
    print("4. Quit")

    choice = input("Enter your choice (1/2/3/4): ")

    if choice == "1":
        task = input("Enter a task to add: ")
        add_task(task)
    elif choice == "2":
        view_tasks()
    elif choice == "3":
        view_tasks()
        index = input("Enter the index of the task to mark as completed (or 0 to cancel): ")
        if index.isdigit():
            index = int(index)
            if index == 0:
                continue
            complete_task(index)
        else:
            print("Invalid input. Please enter a valid task index.")
    elif choice == "4":
        print("Goodbye!")
        break
    else:
        print("Invalid choice. Please choose a valid option (1/2/3/4).")

