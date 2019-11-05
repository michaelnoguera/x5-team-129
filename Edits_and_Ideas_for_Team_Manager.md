# Edits and Ideas for Team Manager

## Description
This program proposals more on helping human decision, not for mechanic automatic decision.
### Symbols
Class size = N
Team size = n
### Assumptions and definitions
1. Assume team maker (the user of this program) give survey to the class every time when group decision is needed.
2. Assume everyone knows each other's name in the class.
3. Assume everyone who is in the class does the survey completely and honestly every time.
4. Define the priority of "do not like to work with" to be -1, and the priority of "want to work with" weights from 1 to n.

## Input
The input file should be a CSV or JSON file each time which contains all the data from each survey.
## Team Size/Number Calculator
When N != 0(mod n), modify some teams' size:
for (int c = 1; c <= (n-1); c++) {
     if n(mod 2) != c(mod 2)
        we have ⌊N/n⌋-1 teams with size n, 1 team with size (n-1) and 1 team with size (n-2);
     if n(mod 2) == c(mod 2)
        we have ⌊N/n⌋-1 teams with size n and 2 teams with size (n-1);
}
## Output
The input file should be a marked CSV or JSON file contains list of teams.

## Directed Graph(s)
Take each team as a directed cyclic graph.
### Vertices
Every vertex contains key, in-degree and out-degree.
Key: the key of the vertex is name of student.
In-degree: in-degree of the vertex(student) represents the number of students who "write down" this student's name, no matter want or dislike.
Out-degree: out-degree of the vertex(student) represents the number of students' name that this student "writes down".
### Edges
Edges are weighted -1 for "do not like to work with" or 1 to n for "how much want to work with", where n is a variable represents team size.
### Subgraphs (for filtered results - missing preferences, leftover vertices)

## User Override

## GUI Figures

## Data Figures



# Criteria

## Title:

## Problem:

## Primary User:

## Front-End (GUI)

## Back-End (Data Structures)
