tasks = []

while True:
    print("\n===== TO-DO LIST =====")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Delete Task")
    print("4. Mark as Done")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        task = input("Enter task: ")
        tasks.append({"task": task, "done": False})
        print("Task Added!")

    elif choice == "2":
        if len(tasks) == 0:
            print("No Tasks Yet!")
        else:
            print("\nYour Tasks:")
            for i, t in enumerate(tasks, 1):
                status = "✓" if t["done"] else "✗"
                print(f"{i}. {t['task']} [{status}]")

    elif choice == "3":
        num = int(input("Enter task number to delete: "))
        if 1 <= num <= len(tasks):
            tasks.pop(num-1)
            print("Task Deleted!")
        else:
            print("Invalid number!")

    elif choice == "4":
        num = int(input("Enter task number to mark done: "))
        if 1 <= num <= len(tasks):
            tasks[num-1]["done"] = True
            print("Task Marked as Done!")
        else:
            print("Invalid number!")

    elif choice == "5":
        print("Thank You!")
        break
    else:
        print("Invalid Choice!")# To-DO-APP-Main.py