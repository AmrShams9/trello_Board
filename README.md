What is Trello? Trello is the visual tool that empowers your team to manage any type of
project, workflow, or task tracking. Add files, checklists, or even automation: Customize
it all for how your team works best. Just sign up, create a board.
You are required to build the backend side for the trello app. This application will allow
users to create boards, lists, and cards to organize their tasks. Users can collaborate
with team members, assign tasks, and track progress. The application will include
features such as RESTful APIs, messaging for real-time updates, and security
authorization to ensure data integrity and confidentiality.
Team Leader can create one or more boards to simulate different projects.
A board comprises three or more lists, such as the TODO list, In Progress list, Testing
list, and Done list. Each list is composed of one or more cards, each representing a
task. These cards include the task description and any accompanying comments.
A collaborator, whether a tester or developer, has the ability to transition a card from the
ToDo list to the In Progress list once they commence work on the task. Subsequently,
the developer moves the card to the Testing column, allowing the tester collaborator to
begin assessing the task. Upon completion of testing and verification by the tester, the
task can then be moved from the Testing list to the Done list.

Functional Requirements:
1. User Management
a. - Users can register for an account with a valid email address and
password.
b. - Users can log in using their credentials.
c. - Users can update their profile information, including name, email, and
password.

2. Board Management (TeamLeader Role only)
a. - Users can create a new board with a unique name.
b. - Users can view all boards they have access to.
c. - Users can invite other users to collaborate on a board.
d. - Users can delete a board they created
3. List Management (TeamLeader Role only)
a. - Users can create lists within a board to categorize tasks.
b. - Users can delete lists.
4. Card Management (Collaborator Role)
a. - Users can create cards within a list to represent individual tasks.
b. - Users can move cards between lists.
c. - Users can assign cards to themselves or other collaborators.
d. - Users can add descriptions and comments to cards.

Messaging System
- Users receive real-time updates when changes are made to boards, lists, or cards as
follows:
When any updates occur to the card, such as changes to the description, the addition or
modification of comments, or alterations to the card status, a new notification will be
sent to both the card assignee and anyone who has commented on the card.
[No new requirements, just clarification]
You must create a standardized event object capable of accommodating various event
types.
Consider triggering the event after the API logic for the following actions is completed:
1. Assigning tasks to collaborators using the Assign Task API.
2. Updating tasks via the Update Task API, which may involve modifying comments,
descriptions, or status changes.
Verification will involve utilizing a message-driven bean or publish-consumer models to
print the received event. The event should be a JSON object containing task updates,
event names, and other relevant information.

Security Authorization
Access to APIs listed under requirements number 1 and 2 is restricted to Team Leader
users exclusively. Any attempt by other users to access these APIs will result in a 403
error. However, all users have permission to execute the remaining APIs.
Extra Requirements for 4-size teams:
1- Advanced Search and Filtering:
Users can have access to multiple boards[one collaborator can work on many
projects].
Create an advances search API to search across boards, lists, and cards using
keywords[match words in ticket title and description ], ticket status, ticket
assignees , ticket reporters[the one who creates the ticket], or creation date of
the ticket
Expected to return a list of tasks that satisfy the filter query
2- Automatic Messages to Assignees and Reporter
The team leader has the capability to set a deadline date for each task. An
automatic notification will be dispatched to the task assignee one day prior to the
deadline, serving as a reminder. In case the deadline passes without completion, a
notification will be sent to the reporter, indicating that the task has exceeded the
deadline, serving as an escalation alert for the delayed task.
Bonus Requirements for ALL teams
1- Sprint Reports
In Agile setups, Trello is often used. Here's how it usually goes: the team leader starts a
sprint, which can last either two weeks or a month. During this time, the team tackles a
set of tasks, maybe around 20. As they work, they move tasks from 'To-Do' to 'In
Progress' to 'Done'. Each task is assigned a 'story point' indicating its importance,
typically following the Fibonacci series like 3, 5, 8, 13, 21. Sometimes, tasks aren't
finished by the sprint's end. When a new sprint begins, any unfinished tasks from the
previous one automatically roll over.
Your job is to create an API for ending a sprint. This API will help start a new sprint,
move unfinished tasks to it, and close the current sprint. Also, you need another API for
generating a report based on a sprint ID, showing sprint metadata, Total completed
story points and Total uncompleted story points
////////////////////////////////////////////
//////////////////////////////////////////////////
