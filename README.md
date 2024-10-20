# todolist

# todo.py

tasks = []

def display_menu():
    print("\nTo-Do List Menu:")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Remove Task")
    print("4. Exit")
def add_task():
    task = input("Enter the task: ")
    tasks.append(task)
    print(f'Task "{task}" added.')
def view_tasks():
    if tasks:
        print("\nYour Tasks:")
        for index, task in enumerate(tasks, start=1):
            print(f"{index}. {task}")
    else:
        print("No tasks available.")
def remove_task():
    view_tasks()
    try:
        index = int(input("Enter the task number to remove: ")) - 1
        if 0 <= index < len(tasks):
            removed_task = tasks.pop(index)
            print(f'Task "{removed_task}" removed.')
        else:
            print("Invalid task number.")
    except ValueError:
        print("Please enter a valid number.")
def main():
    while True:
        display_menu()
        choice = input("Choose an option: ")
        
        if choice == '1':
            add_task()
        elif choice == '2':
            view_tasks()
        elif choice == '3':
            remove_task()
        elif choice == '4':
            print("Goodbye!")
            break
        else:
            print("Invalid choice, please try again.")

if __name__ == "__main__":
    main()
