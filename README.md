# employee-management.py
class Employee:
    def __init__(self, emp_id, name, age, department):
        self.emp_id = emp_id
        self.name = name
        self.age = age
        self.department = department

    def __str__(self):
        return f"ID: {self.emp_id}, Name: {self.name}, Age: {self.age}, Department: {self.department}"

class EmployeeManagement:
    def __init__(self):
        self.employees = {}

    def add_employee(self):
        emp_id = input("Enter employee ID: ")
        if emp_id in self.employees:
            print("Employee ID already exists!")
            return
        name = input("Enter name: ")
        age = input("Enter age: ")
        department = input("Enter department: ")
        self.employees[emp_id] = Employee(emp_id, name, age, department)
        print("Employee added successfully.")

    def view_employees(self):
        if not self.employees:
            print("No employees found.")
            return
        for emp in self.employees.values():
            print(emp)

    def update_employee(self):
        emp_id = input("Enter employee ID to update: ")
        if emp_id not in self.employees:
            print("Employee not found.")
            return
        print("Leave blank to keep current value.")
        name = input(f"Enter new name (current: {self.employees[emp_id].name}): ") or self.employees[emp_id].name
        age = input(f"Enter new age (current: {self.employees[emp_id].age}): ") or self.employees[emp_id].age
        department = input(f"Enter new department (current: {self.employees[emp_id].department}): ") or self.employees[emp_id].department
        self.employees[emp_id] = Employee(emp_id, name, age, department)
        print("Employee updated successfully.")

    def delete_employee(self):
        emp_id = input("Enter employee ID to delete: ")
        if emp_id in self.employees:
            del self.employees[emp_id]
            print("Employee deleted successfully.")
        else:
            print("Employee not found.")

def main():
    em = EmployeeManagement()
    while True:
        print("\nEmployee Management System")
        print("1. Add Employee")
        print("2. View Employees")
        print("3. Update Employee")
        print("4. Delete Employee")
        print("5. Exit")
        choice = input("Enter your choice: ")
        if choice == '1':
            em.add_employee()
        elif choice == '2':
            em.view_employees()
        elif choice == '3':
            em.update_employee()
        elif choice == '4':
            em.delete_employee()
        elif choice == '5':
            print("Exiting program.")
            break
        else:
            pr
