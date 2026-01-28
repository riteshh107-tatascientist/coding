# Employee Management System (EMS)

# Step 1: Data Storage (Dictionary)
employees = {
    101: {'name': 'Satya', 'age': 27, 'department': 'HR', 'salary': 50000},
    102: {'name': 'Aman', 'age': 25, 'department': 'IT', 'salary': 60000}
}

# Function to add a new employee
def add_employee():
    print("\n--- Add New Employee ---")
    
    emp_id = int(input("Enter Employee ID: "))
    
    if emp_id in employees:
        print("❌ Employee ID already exists. Try a new ID.")
        return
    
    name = input("Enter Employee Name: ")
    age = int(input("Enter Employee Age: "))
    department = input("Enter Employee Department: ")
    salary = int(input("Enter Employee Salary: "))
    
    employees[emp_id] = {
        'name': name,
        'age': age,
        'department': department,
        'salary': salary
    }
    
    print("✅ Employee added successfully!")

# Function to view all employees
def view_employees():
    print("\n--- All Employees ---")
    
    if not employees:
        print("No employees available.")
        return
    
    print("ID\tName\tAge\tDepartment\tSalary")
    print("-" * 45)
    
    for emp_id, details in employees.items():
        print(f"{emp_id}\t{details['name']}\t{details['age']}\t{details['department']}\t\t{details['salary']}")

# Function to search an employee by ID
def search_employee():
    print("\n--- Search Employee ---")
    
    emp_id = int(input("Enter Employee ID to search: "))
    
    if emp_id in employees:
        emp = employees[emp_id]
        print("\nEmployee Found ✅")
        print(f"Name       : {emp['name']}")
        print(f"Age        : {emp['age']}")
        print(f"Department : {emp['department']}")
        print(f"Salary     : {emp['salary']}")
    else:
        print("❌ Employee not found.")

# Main Menu Function
def main_menu():
    while True:
        print("\n===== Employee Management System =====")
        print("1. Add Employee")
        print("2. View All Employees")
        print("3. Search for Employee")
        print("4. Exit")
        
        choice = input("Enter your choice (1-4): ")
        
        if choice == '1':
            add_employee()
        elif choice == '2':
            view_employees()
        elif choice == '3':
            search_employee()
        elif choice == '4':
            print("🙏 Thank you for using EMS. Goodbye!")
            break
        else:
            print("❌ Invalid choice. Please try again.")

# Program Start
main_menu()
