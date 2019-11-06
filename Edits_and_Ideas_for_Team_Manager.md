# Edits and Ideas for Team Manager

## Description
This program proposals more on helping human decision, not for mechanic automatic decision.
### Symbols
Class size = N; <br>
Team size = n.
### Assumptions and definitions
1. Assume team maker (the user of this program) give survey to the class every time when group decision is needed.
2. Assume everyone knows each other's name in the class.
3. Assume everyone who is in the class does the survey completely and honestly every time.
4. Define the priority of "do not like to work with" to be positive Infinity, while the priorities of "want to work with" range from `1` to `team size`, where 1 is the first choice for partners.
5. The maximum number of people input is less than or equal to 100.
6. The maximum number of teams is 12.
## Input
The input file should be a CSV file each time which contains all the data from each survey.

## Team Size/Number Calculator
When N != 0(mod n), modify some teams' size:

```Java
for (int c = 1; c <= (n-1); c++) {
     if n(mod 2) != c(mod 2)
        we have ⌊N/n⌋-1 teams with size n, 1 team with size (n-1) and 1 team with size (n-2);
     if n(mod 2) == c(mod 2)
        we have ⌊N/n⌋-1 teams with size n and 2 teams with size (n-1);
} 
```

## Output
The input file should be a marked CSV or JSON file contains list of teams.

## Directed Graph(s)
Take each team as a directed cyclic graph.

### Vertices
Every vertex contains key, in-degree and out-degree.
- Key: the key of the vertex is name of student.
- In-degree: in-degree of the vertex(student) represents the number of students who "write down" this student's name, no matter want or dislike.
- Out-degree: out-degree of the vertex(student) represents the number of students' name that this student "writes down".
- Team ID (array index) 

### Edges
Edges are weighted with a prohibitively large number for "do not like to work with" or 
for desired partners, weighted between `1` and `team size` with smaller numbers being
better. 

### Subgraphs (for filtered results - missing preferences, leftover vertices)
**all**= everybody, the whole graph is shown
**unadded**= subgraph of people who are not currently on a team
**teams**= shows each team as a seperate subgraph

**Different colors** represent what team a person is on. Colors will be chosen from the palette built in to `java.awt.colors`. 

## Automatic Team Generation
- user can override
- at first, use Dijkstra's algorithm to find the shortest path with at least length team size from randomly chosen vertexes (this is slow)

## GUI Figures
- [ ] modify original gui
- [ ] image for each tab
- [ ] colors to show teams
- [x] edit user demonstrates instructor override
- [ ] emphasize capability to add user

## Data Figures
- [ ] show teams as a array-based List of team objects, each containing an array-based List of their constituent members.
- [ ] describe but do not model adjacency list
