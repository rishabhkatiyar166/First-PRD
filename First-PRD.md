# HireReady — Campus Placement Application Checker

## Day 2 Java Team Project

HireReady is a Java console application that checks whether a candidate is eligible to apply for a campus placement opportunity.

Build this project from scratch using only the Java concepts completed so far. Create the project, implement the full requirement, test multiple scenarios, document the results, and push the completed project to GitHub.

---

## 1. Project Objective

Create a Java program that stores a candidate's placement profile and checks whether the candidate can apply for a company hiring drive.

The program must:

- Store candidate details using variables.
- Use suitable Java data types.
- Calculate aptitude and coding percentages.
- Evaluate placement eligibility.
- Identify the first failed eligibility condition.
- Display the final application status.
- Display a suitable next action.

---

## 2. Scenario

A company is conducting a campus placement drive.

Candidates can apply only when they satisfy the company's eligibility requirements.

The company considers:

- Degree percentage
- Active backlogs
- Graduation year
- Aptitude assessment performance
- Coding assessment performance
- Communication assessment performance
- Project completion
- Profile verification

Your application must evaluate one candidate and display whether the candidate is eligible to apply.

---

## 3. Concepts You May Use

Use only the concepts completed in class:

- Java program structure
- `main()` method
- `System.out.print()`
- `System.out.println()`
- Variables
- Primitive data types
- `String`
- Variable naming rules
- Type conversion
- Type casting
- Integer division
- Decimal division
- Arithmetic operators
- Assignment operators
- Relational operators
- Logical operators
- Operator precedence
- String concatenation
- Boolean expressions
- `if`
- `else if`
- `else`
- Nested conditions
- Compound conditions

---

## 4. Concepts You Must Not Use

Do not use concepts that have not yet been completed:

- `Scanner`
- User input
- Loops
- Arrays
- User-defined methods
- Multiple custom classes
- Objects
- Collections
- Exception handling
- File handling
- Database connectivity

Use fixed values inside `Main.java`.

Test the application by manually changing these values and running the program again.

---

## 5. Project Structure

Create the project using the following structure:

```text
HireReady/
│
├── README.md
├── src/
│   └── Main.java
└── output/
    └── sample-output.txt
```

| File | Purpose |
|---|---|
| `README.md` | Contains the project requirements, team details, contributions, and test results |
| `src/Main.java` | Contains the complete Java program |
| `output/sample-output.txt` | Contains one complete program output |

---

## 6. Candidate Profile

Store the following candidate information:

| Information | Data Type | Example |
|---|---|---|
| Candidate name | `String` | `"Aarav"` |
| Registration number | `int` | `24031` |
| Degree | `String` | `"B.E. Computer Science"` |
| Graduation year | `int` | `2026` |
| Degree percentage | `double` | `72.5` |
| Active backlogs | `int` | `0` |
| Aptitude correct answers | `int` | `38` |
| Aptitude total questions | `int` | `50` |
| Coding test cases passed | `int` | `8` |
| Coding total test cases | `int` | `10` |
| Communication score | `int` | `68` |
| Project completed | `boolean` | `true` |
| Profile verified | `boolean` | `true` |

Suggested variables:

```java
String candidateName = "Aarav";
int registrationNumber = 24031;
String degree = "B.E. Computer Science";
int graduationYear = 2026;
double degreePercentage = 72.5;
int activeBacklogs = 0;

int aptitudeCorrectAnswers = 38;
int aptitudeTotalQuestions = 50;

int codingTestCasesPassed = 8;
int codingTotalTestCases = 10;

int communicationScore = 68;

boolean projectCompleted = true;
boolean profileVerified = true;
```

You may use different fixed values, but all required fields must remain in the program.

---

## 7. Company Eligibility Rules

A candidate is eligible to apply only when all the following conditions are satisfied:

1. Degree percentage is at least `60`.
2. The candidate has no active backlogs.
3. Graduation year is `2025`, `2026`, or `2027`.
4. Aptitude percentage is at least `60`.
5. Coding percentage is at least `70`.
6. Communication score is at least `60`.
7. The required project is completed.
8. The candidate profile is verified.

---

## 8. Calculate the Aptitude Percentage

Use the following formula:

```text
Aptitude Percentage =
Correct Answers / Total Questions × 100
```

Avoid integer division.

Incorrect:

```java
double aptitudePercentage =
        aptitudeCorrectAnswers / aptitudeTotalQuestions * 100;
```

Correct:

```java
double aptitudePercentage =
        (double) aptitudeCorrectAnswers
        / aptitudeTotalQuestions
        * 100;
```

For `38` correct answers out of `50`, the result must be:

```text
76.0
```

---

## 9. Calculate the Coding Percentage

Use the following formula:

```text
Coding Percentage =
Test Cases Passed / Total Test Cases × 100
```

Use casting before division:

```java
double codingPercentage =
        (double) codingTestCasesPassed
        / codingTotalTestCases
        * 100;
```

For `8` test cases passed out of `10`, the result must be:

```text
80.0
```

---

## 10. Create Boolean Expressions

Create a separate Boolean variable for every eligibility condition.

```java
boolean degreeEligible =
        degreePercentage >= 60;

boolean backlogEligible =
        activeBacklogs == 0;

boolean graduationYearEligible =
        graduationYear >= 2025
        && graduationYear <= 2027;

boolean aptitudeEligible =
        aptitudePercentage >= 60;

boolean codingEligible =
        codingPercentage >= 70;

boolean communicationEligible =
        communicationScore >= 60;

boolean projectEligible =
        projectCompleted;

boolean verificationEligible =
        profileVerified;
```

Create one combined condition:

```java
boolean applicationEligible =
        degreeEligible
        && backlogEligible
        && graduationYearEligible
        && aptitudeEligible
        && codingEligible
        && communicationEligible
        && projectEligible
        && verificationEligible;
```

---

## 11. Final Application Status

Display only one final status.

Possible statuses:

- `Eligible to Apply`
- `Not Eligible`
- `Application On Hold`

### Eligible to Apply

Display this when all eligibility conditions are satisfied.

### Not Eligible

Display this when the candidate fails any of the following:

- Degree percentage
- Active backlog
- Graduation year
- Aptitude percentage
- Coding percentage
- Communication score

### Application On Hold

Display this when the candidate satisfies the performance requirements but:

- The project is incomplete, or
- The profile is not verified

---

## 12. Condition Priority

Check conditions in this order:

1. Degree percentage
2. Active backlogs
3. Graduation year
4. Aptitude percentage
5. Coding percentage
6. Communication score
7. Project completion
8. Profile verification
9. Final eligibility

Display the first important issue the candidate must resolve.

---

## 13. Required Decision Logic

Use `if`, `else if`, and `else`.

```java
if (!degreeEligible) {
    System.out.println("Application Status : Not Eligible");
    System.out.println(
        "Next Action        : Improve the required degree percentage."
    );
} else if (!backlogEligible) {
    System.out.println("Application Status : Not Eligible");
    System.out.println(
        "Next Action        : Clear all active backlogs."
    );
} else if (!graduationYearEligible) {
    System.out.println("Application Status : Not Eligible");
    System.out.println(
        "Next Action        : Check the eligible graduation-year criteria."
    );
} else if (!aptitudeEligible) {
    System.out.println("Application Status : Not Eligible");
    System.out.println(
        "Next Action        : Improve aptitude assessment performance."
    );
} else if (!codingEligible) {
    System.out.println("Application Status : Not Eligible");
    System.out.println(
        "Next Action        : Improve coding assessment performance."
    );
} else if (!communicationEligible) {
    System.out.println("Application Status : Not Eligible");
    System.out.println(
        "Next Action        : Improve communication assessment performance."
    );
} else if (!projectEligible) {
    System.out.println("Application Status : Application On Hold");
    System.out.println(
        "Next Action        : Complete the required project."
    );
} else if (!verificationEligible) {
    System.out.println("Application Status : Application On Hold");
    System.out.println(
        "Next Action        : Complete profile verification."
    );
} else {
    System.out.println("Application Status : Eligible to Apply");
    System.out.println(
        "Next Action        : Submit the company application."
    );
}
```

Do not add this logic without understanding each condition.

---

## 14. Mandatory Program Requirements

Your application must:

1. Contain a class named `Main`.
2. Contain the `main()` method.
3. Store the complete candidate profile.
4. Use suitable Java data types.
5. Calculate aptitude percentage.
6. Calculate coding percentage.
7. Use casting before division.
8. Use arithmetic operators.
9. Use relational operators.
10. Use logical operators.
11. Create Boolean expressions.
12. Use at least one compound condition.
13. Use `if`, `else if`, and `else`.
14. Display the candidate's complete profile.
15. Display assessment percentages.
16. Display individual eligibility results.
17. Display one final application status.
18. Display one next action.
19. Run without `Scanner`.
20. Compile without errors.

---

## 15. Suggested Program Structure

Write the program from scratch.

```java
public class Main {
    public static void main(String[] args) {

        // Candidate profile

        // Aptitude and coding percentage calculations

        // Individual eligibility conditions

        // Combined eligibility condition

        // Candidate profile display

        // Assessment result display

        // Final status and next action
    }
}
```

---

## 16. Expected Output

Your output must be clean and readable.

```text
================================================
        CAMPUS PLACEMENT APPLICATION REPORT
================================================

Candidate Name          : Aarav
Registration Number     : 24031
Degree                  : B.E. Computer Science
Graduation Year         : 2026
Degree Percentage       : 72.5
Active Backlogs         : 0

------------------------------------------------
Aptitude Score          : 38 / 50
Aptitude Percentage     : 76.0
Coding Test Cases       : 8 / 10
Coding Percentage       : 80.0
Communication Score     : 68
Project Completed       : Yes
Profile Verified        : Yes

------------------------------------------------
Degree Eligibility      : Eligible
Backlog Eligibility     : Eligible
Graduation Year         : Eligible
Aptitude Eligibility    : Eligible
Coding Eligibility      : Eligible
Communication Status    : Eligible

------------------------------------------------
Application Status      : Eligible to Apply
Next Action             : Submit the company application
================================================
```

You may improve the formatting, but all required details must appear.

---

## 17. Display Meaningful Boolean Results

Do not display only `true` or `false` in the final report.

Instead of:

```text
Project Completed: true
```

Display:

```text
Project Completed: Yes
```

Example:

```java
if (projectCompleted) {
    System.out.println("Project Completed : Yes");
} else {
    System.out.println("Project Completed : No");
}
```

Use the same approach for profile verification and eligibility results.

---

## 18. Mandatory Test Cases

Test the program by changing the fixed values in `Main.java`.

Compile and run the program after every change.

### Test Case 1 — Eligible Candidate

```text
Degree Percentage: 72.5
Active Backlogs: 0
Graduation Year: 2026
Aptitude: 38 / 50
Coding: 8 / 10
Communication Score: 68
Project Completed: true
Profile Verified: true
```

Expected:

```text
Eligible to Apply
```

### Test Case 2 — Low Degree Percentage

```text
Degree Percentage: 58
```

Expected:

```text
Not Eligible
Next Action: Improve the required degree percentage
```

### Test Case 3 — Active Backlogs

```text
Active Backlogs: 2
```

Expected:

```text
Not Eligible
Next Action: Clear all active backlogs
```

### Test Case 4 — Ineligible Graduation Year

```text
Graduation Year: 2024
```

Expected:

```text
Not Eligible
Next Action: Check the eligible graduation-year criteria
```

### Test Case 5 — Low Aptitude Performance

```text
Aptitude Correct Answers: 25
Aptitude Total Questions: 50
```

Expected aptitude percentage:

```text
50.0
```

Expected:

```text
Not Eligible
Next Action: Improve aptitude assessment performance
```

### Test Case 6 — Low Coding Performance

```text
Coding Test Cases Passed: 6
Coding Total Test Cases: 10
```

Expected coding percentage:

```text
60.0
```

Expected:

```text
Not Eligible
Next Action: Improve coding assessment performance
```

### Test Case 7 — Low Communication Score

```text
Communication Score: 55
```

Expected:

```text
Not Eligible
Next Action: Improve communication assessment performance
```

### Test Case 8 — Project Incomplete

```text
Project Completed: false
```

Expected:

```text
Application On Hold
Next Action: Complete the required project
```

### Test Case 9 — Profile Not Verified

```text
Profile Verified: false
```

Expected:

```text
Application On Hold
Next Action: Complete profile verification
```

### Test Case 10 — Exact Boundary Values

```text
Degree Percentage: 60
Active Backlogs: 0
Graduation Year: 2025
Aptitude Correct Answers: 30
Aptitude Total Questions: 50
Coding Test Cases Passed: 7
Coding Total Test Cases: 10
Communication Score: 60
Project Completed: true
Profile Verified: true
```

Expected:

```text
Aptitude Percentage: 60.0
Coding Percentage: 70.0
Application Status: Eligible to Apply
```

### Test Case 11 — Multiple Failed Conditions

```text
Degree Percentage: 55
Active Backlogs: 2
Aptitude Correct Answers: 20
Aptitude Total Questions: 50
Coding Test Cases Passed: 5
Coding Total Test Cases: 10
```

Expected:

```text
Application Status: Not Eligible
Next Action: Improve the required degree percentage
```

Only the first failed condition must be displayed.

---

## 19. Test Result Table

Complete this table after running every test.

| Test ID | Scenario | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| TC-01 | All requirements satisfied | Eligible to Apply |  |  |
| TC-02 | Degree percentage below 60 | Not Eligible |  |  |
| TC-03 | Active backlogs | Not Eligible |  |  |
| TC-04 | Invalid graduation year | Not Eligible |  |  |
| TC-05 | Aptitude below 60% | Not Eligible |  |  |
| TC-06 | Coding below 70% | Not Eligible |  |  |
| TC-07 | Communication below 60 | Not Eligible |  |  |
| TC-08 | Project incomplete | Application On Hold |  |  |
| TC-09 | Profile not verified | Application On Hold |  |  |
| TC-10 | Exact boundary values | Eligible to Apply |  |  |
| TC-11 | Multiple failed conditions | First failure displayed |  |  |

Replace the empty columns after executing the tests.

---

## 20. Team Responsibilities

Assign responsibilities before starting development.

### Team Lead

- Create the GitHub repository.
- Divide the project into tasks.
- Track task completion.
- Review changes before pushing.
- Ensure every member contributes.

### Requirement Member

- Read the complete README.
- Identify inputs, calculations, conditions, and outputs.
- Prepare the condition priority.

### Data and Calculation Member

- Create candidate variables.
- Select suitable data types.
- Implement aptitude and coding calculations.
- Verify casting and decimal division.

### Logic Member

- Create Boolean expressions.
- Implement eligibility conditions.
- Implement final status logic.

### Testing Member

- Execute all mandatory test cases.
- Record expected and actual results.
- Verify exact boundary values.

### Documentation Member

- Update the README.
- Add team details.
- Add contribution details.
- Add test results and the learning summary.

### Reviewer and Presenter

- Review the complete program.
- Confirm that restricted concepts are not used.
- Explain the application and code.

Roles may be combined when a team has fewer members.

---

## 21. Participation Requirement

Every team member must complete at least two meaningful contributions.

Examples:

- Created candidate-profile variables.
- Selected and explained data types.
- Calculated aptitude percentage.
- Calculated coding percentage.
- Added type casting.
- Created Boolean expressions.
- Implemented one conditional block.
- Created test cases.
- Tested boundary values.
- Corrected a logical error.
- Improved output formatting.
- Updated project documentation.
- Created a meaningful Git commit.
- Explained part of the application.

Presence without contribution is not considered participation.

---

## 22. Team Details

Complete this section:

```text
Team Name:

Team Lead:

Team Members:

1.
2.
3.
4.
5.
6.
7.
```

---

## 23. Contribution Table

| Member Name | Responsibility | Work Completed | Commit Message |
|---|---|---|---|
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

Every member must be able to explain the work listed in this table.

---

## 24. Build the Project

### Step 1 — Create the Project Folder

```bash
mkdir HireReady
cd HireReady
```

### Step 2 — Create the Required Folders

```bash
mkdir src
mkdir output
```

### Step 3 — Create the Java File

Create:

```text
src/Main.java
```

### Step 4 — Create the README

Create:

```text
README.md
```

### Step 5 — Write the Java Program

Build the complete program inside:

```text
src/Main.java
```

### Step 6 — Compile the Program

```bash
javac src/Main.java
```

### Step 7 — Run the Program

```bash
java -cp src Main
```

### Step 8 — Execute the Test Cases

For every test case:

1. Change the fixed values.
2. Save `Main.java`.
3. Compile the program.
4. Run the program.
5. Compare expected and actual results.
6. Update the test table.

### Step 9 — Save the Sample Output

Copy one complete output into:

```text
output/sample-output.txt
```

---

## 25. Push the Project to GitHub

### Initialize Git

```bash
git init
```

### Check the Files

```bash
git status
```

### Add the Initial Files

```bash
git add .
```

### Create the First Commit

```bash
git commit -m "Create HireReady project structure"
```

### Add Candidate Profile

```bash
git add .
git commit -m "Add candidate profile and assessment data"
```

### Add Calculations

```bash
git add .
git commit -m "Calculate aptitude and coding percentages"
```

### Add Eligibility Logic

```bash
git add .
git commit -m "Implement placement eligibility conditions"
```

### Add Testing and Documentation

```bash
git add .
git commit -m "Add test results and project documentation"
```

### Connect the Repository

```bash
git remote add origin <repository-url>
```

### Push the Project

```bash
git branch -M main
git push -u origin main
```

Replace `<repository-url>` with your GitHub repository URL.

---

## 26. Git Requirements

Your repository must contain at least four meaningful commits.

Recommended commits:

1. `Create HireReady project structure`
2. `Add candidate profile and assessment data`
3. `Calculate aptitude and coding percentages`
4. `Implement placement eligibility conditions`
5. `Add formatted application report`
6. `Add test results and documentation`

Do not use unclear commit messages such as:

```text
update
changes
final
done
code
```

---

## 27. Coding Standards

### Use Meaningful Names

Use:

```java
double aptitudePercentage;
boolean codingEligible;
int activeBacklogs;
```

Avoid:

```java
double a;
boolean result;
int x;
```

### Use Consistent Formatting

```java
if (codingEligible) {
    System.out.println("Coding Eligibility: Eligible");
} else {
    System.out.println("Coding Eligibility: Not Eligible");
}
```

### Use Correct Operators

Use `=` to assign a value:

```java
int activeBacklogs = 0;
```

Use `==` to compare values:

```java
boolean backlogEligible = activeBacklogs == 0;
```

### Avoid Integer Division

```java
double aptitudePercentage =
        (double) aptitudeCorrectAnswers
        / aptitudeTotalQuestions
        * 100;
```

### Use Comments Only Where Required

Good:

```java
// Calculate coding performance as a percentage
```

Avoid:

```java
// Create an integer variable
int communicationScore = 68;
```

---

## 28. Restrictions

Do not:

- Use `Scanner`.
- Use loops.
- Use arrays.
- Create user-defined methods.
- Create additional custom classes.
- Use collections.
- Copy another team's completed program.
- Add code that your team cannot explain.
- Push only the `.class` file.
- Submit screenshots without source code.
- Remove failed test results.
- Use only one Git commit.
- Upload unnecessary IDE-generated files.

---

## 29. Required Repository Content

Your final repository must contain:

```text
HireReady/
│
├── README.md
├── src/
│   └── Main.java
└── output/
    └── sample-output.txt
```

Do not commit generated files such as:

```text
Main.class
.idea/
.vscode/
```

unless specifically required.

---

## 30. Project Summary

Complete this section after finishing the application.

### What We Built

Describe the application in two to four sentences.

### Java Concepts Used

Mention all Java concepts used in the project.

### Calculation Implemented

Explain how aptitude and coding percentages were calculated.

### Most Difficult Condition

Explain which eligibility condition was difficult to implement.

### Integer Division Issue

Explain what happened before casting and how it was corrected.

### Boundary Value Learned

Explain why exact values such as `60` and `70` are accepted.

### Logical Error Corrected

Describe one error found during testing.

### Team Collaboration

Explain how the work was divided.

### Next Feature

Mention one feature that can be added after learning the next Java concept.

---

## 31. Individual Reflection

Every team member must complete this section:

```text
Name:

Role:

My main contribution:

One variable I created:

One data type I selected:

One calculation I explained:

One Boolean expression I created:

One condition I implemented:

One test case I executed:

One mistake I identified:

One thing I learned from the team:

One improvement I will make:
```

---

## 32. Completion Checklist

- [ ] The project folder is named `HireReady`
- [ ] `README.md` is completed
- [ ] `src/Main.java` exists
- [ ] `output/sample-output.txt` exists
- [ ] The program compiles successfully
- [ ] The program runs without `Scanner`
- [ ] All candidate details are stored
- [ ] Appropriate data types are used
- [ ] Aptitude percentage is calculated
- [ ] Coding percentage is calculated
- [ ] Casting is used before division
- [ ] Arithmetic operators are used
- [ ] Relational operators are used
- [ ] Logical operators are used
- [ ] Boolean expressions are created
- [ ] Compound conditions are used
- [ ] `if`, `else if`, and `else` are used
- [ ] One application status is displayed
- [ ] One next action is displayed
- [ ] All mandatory test cases are completed
- [ ] Boundary values are tested
- [ ] Test results are documented
- [ ] Team contributions are documented
- [ ] At least four meaningful commits exist
- [ ] The project is pushed to GitHub
- [ ] Every member understands the complete application

---

## 33. Final Submission

Complete the following:

```text
Team Name:

Team Lead:

GitHub Repository URL:

Total Team Members:

Total Commits:

Total Test Cases:

Passed Test Cases:

Failed Test Cases:

Final Project Status:
```

The project is complete only when the application works correctly, the documentation is updated, all required test cases are executed, and the repository is available on GitHub.
