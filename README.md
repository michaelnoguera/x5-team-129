# x5-team-129

### Project Title: Team Manager Graph

### Team Members:
Bingyu Mao
Michael Nogeura
Shannon Stiles

## Problem
Oftentimes groups need to be made out of a pool of individuals for collaborative work in classes or competition teams. A science teacher might want to group students to work together on a lab, or a club advisor might have to determine teams of members for small-group competitions. Everybody has opinions of who they do and do not want to work with, but it seems they are always unsatisfied with the groups they are put in by their teacher or advisor.

## Primary stakeholder
**Team Maker** intends to help teachers solve the problem of making groups that are satisfactory to all involved. However, anybody in charge of making teams can use it.
Thus Team Maker’s primary users will be teachers, club advisors, camp counselors, and anyone else who needs to easily make groups in a way that satisfies as many people as possible.

## User Interface
Team Maker’s user interface consists of a main window that shows people’s team preferences graphically in a large web. 

Users can modify the student nodes using the buttons on the right hand side of the window. They can select a person and edit that person's parameters, delete that person, or assign them to a team. Beneath the person-specific settings, the options to change team size and the number of teams are readily available.

Lists of people on each team are shown at the bottom of the screen. Both these lists and the web graphic will be updated in real time. One way that this helps is that if two people who have expressed a conflict in working with each other are added to the same team, a warning icon is shown by their names in the team list (see team 3 in the first image below). In addition, full teams will be grayed out in the sidebar so that no team exceeds the maximum capacity (see team 5 in the first image).

Here are some images of what the user interface might look like.
Main window.

Splash screen shown on startup, gives option to create a new empty project from scratch, or to import CSV data.
Edit user dialog, used to change a user’s name or edit their team preferences.

## Data
To use Team Maker, the teacher will first decide on the group size and the number of groups they want to make.

The teacher can add student data directly from the graphical interface, or by using the CSV (Comma-Separated Values) file import function. CSV is an ideal file format for storing the team preferences of each student because the data gathered lends itself well to being represented in list form. Also, many polling platforms support CSV export.

Ideally, students would submit their lists of ideal partners via a Google Form, which could be exported from Google Sheets into a CSV file by the teacher. It is recommended that a dropdown box with a list of student names is used on the form so that the output from the form has consistent capitalization and spelling.

> This is an example of what CSV partner data could look like. Note that no columns are required (except the first), so it is possible for Jane in line six to leave the two `yes` fields blank while asking to be put in a different group from Jim.
'' Name, Yes 1, Yes 2, No 1, No 2
'' Jim, Joe, Jane, Jeramiah, Jessica
'' Joe, Steve, Jim
'' Mary, Scott, Steve, Charlie
'' Jeramiah, Scott, Mary
'' Jane, , , Jim

Team preference data data will be stored in a directed graph by the program, representing each person as a node. Weighted edges will connect people with peers that they do or do not want to work with. A positive weight means that they do want to be in a group with the other individual, a negative weight means that that they do not. Weights will be integers instead of booleans to leave the program open to later additions, such as adding the ability to rank partners in order.
The teams themselves will be stored in an 2D array of nodes with dimensions determined by the group size and number of groups entered by the user. This is ideal because each team has a semi-fixed size (which can change, but is unlikely to change frequently), and there are a semi-fixed number of teams.
When the user decides to export the groups, the contents of the arrays will be formatted according to markdown styles and written to a text file in the current working directory.
