# Employee Management System

Name: Moaz Wael Ezzat  
ID: 2300332

A Java OOP project that implements the provided UML class diagram.

## Classes

- `Employee` - abstract base class.
- `CommissionEmployee` - employee paid by base salary plus commission.
- `MonthlyEmployee` - employee paid monthly with a bonus percentage.
- `HourlyEmployee` - employee paid according to regular and overtime hours.
- `Department` - manages employees and calculates total payroll.
- `Gender` - enum containing `MALE` and `FEMALE`.

## Project Structure

```text
EmployeeManagementSystem/
├── src/
│   ├── Main.java
│   └── model/
│       ├── Employee.java
│       ├── CommissionEmployee.java
│       ├── MonthlyEmployee.java
│       ├── HourlyEmployee.java
│       ├── Department.java
│       └── Gender.java
├── test/
│   └── MainTest.java
└── README.md
```

## Requirements

- JDK 17 or newer
- Any Java IDE such as IntelliJ IDEA, Eclipse, NetBeans, or VS Code

## Running

Open the project in your IDE and run:

```text
src/Main.java
```

To run the simple checks in `MainTest.java`, enable Java assertions and run:

```text
test/MainTest.java
```

From a terminal, one simple way to compile and run the project is:

```bash
mkdir -p out
javac -d out src/model/*.java src/Main.java
java -cp out Main
```

To run the test class:

```bash
javac -d out src/model/*.java test/MainTest.java
java -ea -cp out MainTest
```

## Implementation Notes

The UML diagram specifies the class structure and method names, but it does not explicitly state every business rule for salary calculations. The implementation therefore uses these reasonable rules:

- Commission salary = `baseSalary + (salesAmount * commissionRate)`.
- Monthly salary = `monthlySalary + (monthlySalary * bonusPercentage)`.
- Additional vacation = `max(0, vacationDays - 21)`.
- Hourly salary uses 40 regular hours; hours above 40 are paid using `overtimeRate`.
- Department payroll is the sum of `calculateSalary()` for all employees.

If your instructor provided separate written rules for these calculations, replace only the corresponding method bodies while keeping the UML structure unchanged.

## GitHub

Create a public repository named `EmployeeManagementSystem`, then push this project.

Example commands:

```bash
git init
git add .
git commit -m "Implement employee management system"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```
