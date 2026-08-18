# HireReady — Campus Placement Application Checker

HireReady is a Java console application that stores a candidate's academic and assessment profile and determines their eligibility for campus recruitment drives based on company-specific criteria.

---

## 1. Project Overview & Scenario
The program evaluates a candidate's profile against hiring eligibility requirements. It computes test percentages, checks all rules in priority order, and outputs a formatted report detailing the candidate’s status and required next steps.

---

## 2. Project Structure

```text
HireReady/
│
├── README.md
├── src/
│   └── Main.java
└── output/
    └── sample-output.txt

## 3. Eligibility Criteria & Priority Rules

A candidate is evaluated strictly in the following priority order:  
1. Degree Percentage: Must be at least 60% (>= 60).  
2. Active Backlogs: Must have zero active backlogs (== 0).  
3. Graduation Year: Must be 2025, 2026, or 2027.  
4. Aptitude Percentage: Must be at least 60% (>= 60).  
5. Coding Percentage: Must be at least 70% (>= 70).  
6. Communication Score: Must be at least 60 (>= 60).  
7. Project Completion: Must be completed (true).  
8. Profile Verification: Must be verified (true).  