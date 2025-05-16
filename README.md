# Simple-To-Do-List
def show_menu():
    print("\nTo-Do List Menu:")
    print("1. View tasks")
    print("2. Add a task")
    print("3. Remove a task")
    print("4. Exit")

def view_tasks(tasks):
    if not tasks:
        print("Your to-do list is empty.")
    else:
        print("\nYour To-Do List:")
        for idx, task in enumerate(tasks, 1):
            print(f"{idx}. {task}")

def add_task(tasks):
    task = input("Enter the task you want to add: ").strip()
    if task:
        tasks.append(task)
        print(f'"{task}" has been added.')
    else:
        print("Cannot add an empty task.")

def remove_task(tasks):
    view_tasks(tasks)
    if tasks:
        try:
            task_num = int(input("Enter the number of the task to remove: "))
            if 1 <= task_num <= len(tasks):
                removed = tasks.pop(task_num - 1)
                print(f'"{removed}" has been removed.')
            else:
                print("Invalid task number.")
        except ValueError:
            print("Please enter a valid number.")

def todo_list_app():
    tasks = []

    while True:
        show_menu()
        choice = input("Choose an option (1-4): ").strip()

        if choice == '1':
            view_tasks(tasks)
        elif choice == '2':
            add_task(tasks)
        elif choice == '3':
            remove_task(tasks)
        elif choice == '4':
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Please select from 1 to 4.")

# Run the to-do list app
todo_list_app()
