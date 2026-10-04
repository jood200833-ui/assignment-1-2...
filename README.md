# assignment-1-2...
using System;

public class Person
{
    public string Name { get; set; }
    public string Email { get; set; }

    public Person(string name, string email)
    {
        Console.WriteLine("Person constructor called");
        Name = name;
        Email = email;
    }

    public void DisplayBasicInfo()
    {
        Console.WriteLine($"Name: {Name}, Email: {Email}");
    }
}

public class Student : Person
{
    public int StudentId { get; set; }
    public double GPA { get; set; }

    public Student(string name, string email, int studentId, double gpa) : base(name, email)
    {
        Console.WriteLine("Student constructor called");
        StudentId = studentId;
        GPA = gpa;
    }
}

public class Employee : Person
{
    public int EmployeeId { get; set; }
    public decimal Salary { get; set; }

    public Employee(string name, string email, int employeeId, decimal salary) : base(name, email)
    {
        Console.WriteLine("Employee constructor called");
        EmployeeId = employeeId;
        Salary = salary;
    }
}

public class Teacher : Employee
{
    public string CourseName { get; set; }

    public Teacher(string name, string email, int employeeId, decimal salary, string courseName) 
        : base(name, email, employeeId, salary)
    {
        Console.WriteLine("Teacher constructor called");
        CourseName = courseName;
    }

    public void Teach()
    {
        Console.WriteLine($"Teaching course: {CourseName}");
    }
}

class Program
{
    static void Main()
    {
        Console.WriteLine("--- Creating Student ---");
        Student student = new Student("Sara", "sara@example.com", 101, 3.8);
        student.DisplayBasicInfo();

        Console.WriteLine("\n--- Creating Teacher ---");
        Teacher teacher = new Teacher("Ahmed", "ahmed@example.com", 501, 6000, "Programming");
        teacher.DisplayBasicInfo();
        teacher.Teach();
    }
}