# Classroom 
A room in which a class of pupils or students is taught. In our context, we are representing those in online.

# Student
Students are people in the classroom. We have two different type of students.
1. `Roaster student` - Student who are assigned in class by teacher.
2. `Normal student` - Student who are joining in the class on their own. (using class link or individual signup)

# Co-Teachers
Co-teaching is an educational method that involves two or more teachers working together to plan a classroom and make assessments on group of students. The teacher who create the classroom are called owner of the classroom and have full controll to the classroom including features like add other teachers, delete classroom, edit class details, add/edit students and their marks, edit grade scale and can make others as owner. But if teacher make other as owner, then they will loose the owner title. Idealy each classroom can have only one owner and multiple co-teachers. Co-teacher has all features like owner except they can't delete the classroom.

# Gradescale
Generally, the grading system is the process by which educators evaluate the performance of the pupils in exams on the standard particular scales which is based on the points entirely and consist of the grades like A-Z or range like 1-10; generally, letters and numbers are used to describe the grades of the scholars.

# Gradebook
Gradebook is a record for managing marks of students across tests in the classroom by teacher.


## Working philosophy
- Teacher creates a classroom.
- Teacher can add students and co-teachers.
- By default Points/Percentage is choosen as gradescale. if teacher wants, they can update the gradescale whenever they want. 
- Teacher can create a assessment if they added students.
- Finally, they can view the analysis of student and assessment. 

### Detailed flow
1. Create Classroom
  - Teacher can create new classroom from sidebar "+" button near the Classroom (ablve the class list) and in home screen at final in the classroom list.
  - With class emoji, class name, class subject

2. Add Student
  - While creating classroom itself, we will ask teacher to add students. After classroom creation, teacher can add new students from Student Tab.
  - Can add directly by entering their names.
  - Stident can join in the classroom using specific class link.
  - Can add students from other classes
  
3. New Assessment
  - This option is available in Gradebook tab.
  - With title, date, score type, total points,is it to be consider as main exam or not (with this alone, teacher can create assessment)
  - If score type is `Points`, then teacher will have a option convert total points.
  - If teacher wants to select `Grade` as score type, then we have to make sure the grade scale is not in `Points/Percentage`. If `Points/Percentage` is choosen as grade scale, we will redirect teacher to change the grade scale. 
  - After creating assessment, teacher can add/edit marks of the student.

4. Edit Grade Scale
  - Under settings page, Grade scale tab available.
  - Teacher can change the grade scale from the select box or can create new one.
  - Edit option given for already choosen systm.

5. Co-Teachers
  - Under settings page, Co-Teachers tab available and at individual classroom near profile pic.
  - Can invite other teacher by their email, after other teacher accepts the invitation, they will be added to classroom.
  - Can join using class link

6. Class Deatils Edit/Delete
  - Under settings page, Class Deatils tab available.

7. Edit/Delete assessmwnt
  - Under gradebook tab, for every assessment title box hover.


## Other Features
### In Student 
  * Sort by - asending | decending
  * Export student list as pdf
  * Vew student join request list

### In Gradebook
  * View gradebook in full screen
  * Display as - Points | Percentage | Grade
  * Filter assessment by date and by exams (only main exams)
  * Export the gradebook as pdf
  * View Test wise analysis (by hovering assessment details)
  * View Student wise analysis (by hovering student name)
  * Sort student by mark wise

### Sidebar collapse  

* Attendance tab for now, doesn't have any functionality. Now, it only asks teacher for thier suggestion about what need to be thair at this place.
* Teacher can invite others to join our family by Invite Teacher button at bottom of sidebar.


### Variables used 
## role

| Value | Description |
| :---: | :---: |
| 1 | school admin |
| 4 | teacher |
| 5 | student |


## testStatus
| Value | Description |
| :---: | :---: |
| 0 | present |
| 1 | absent |
| 2 | excused |

- `present` - default.
- `absent` - mark/percentage/grade can be only the lowest (i.e. 0 for points and percentage and lowest grade). teacher can't change that. 
- `excused` - teacher can change the mark.


## role(teacher)
| Value | Description |
| :---: | :---: |
| 0 | class-owner |
| 1 | co-teacher |

- class can have only one owner but multiple co-teacher.


## markingSystem
| Value | Description |
| :---: | :---: |
| 0 | points/marks |
| 1 | grades |

