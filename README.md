-- Create Students Table
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(100),
    Email VARCHAR(100),
    Phone VARCHAR(20),
    Department VARCHAR(50)
);

-- Create Teachers Table
CREATE TABLE Teachers (
    TeacherID INT PRIMARY KEY,
    Name VARCHAR(100),
    Email VARCHAR(100),
    Phone VARCHAR(20),
    Department VARCHAR(50)
);

-- Create Books Table
CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(100),
    Author VARCHAR(100),
    Category VARCHAR(50),
    ISBN VARCHAR(20)
);

-- Create Issues Table
CREATE TABLE Issues (
    IssueID INT PRIMARY KEY AUTO_INCREMENT,
    BookID INT,
    PersonID INT,
    PersonType ENUM('Student', 'Teacher'),
    IssueDate DATE,
    ReturnDate DATE,
    Fine DECIMAL(5,2),
    FOREIGN KEY (BookID) REFERENCES Books(BookID),
    FOREIGN KEY (PersonID) REFERENCES Students(StudentID) -- or Teachers(TeacherID) based on your ER design.
);
