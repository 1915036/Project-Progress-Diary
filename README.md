# Project-Progress-Diary:
 ## **Adminstrator Report for Moodle**:point_down: ##

➡️ **(7-17)-03-23:**

1.Installede Moodle on system.

2.Add the courses and category according to our requirement.
- According to project we add some courses like English,Hindi,Math etc in particular category like 1st,2nd class.
- Create a attendance session in particular course.
- check the Attandence report.

3.Create the users.

4.Give specific roles like (Teacher,student,rich admin) to corresponding users.

:arrow_right: **(26-31)-03-23:**

1.To track the Teachers activites check all the possibilities like teacher or user logs,today losgs.

2.In Report section get the reports of particular coures and the acctivites og user in the courses.

3.Add the *Report Builder* API in moodle.

- **Report builder api** 
System reports are a consistent way of providing reporting data, with paging, filtering, exporting standardized across them. Once the groundwork is done in defining the report elements in entities, it's possible to implement them with minimal code just by adding entities to the report, and defining which elements you want to use from them. 

4.In moodle did work on report builder api and generate the csv of all the columns ,filters and sorting process.

➡️ **(3-14)-03-23:**

1.Installed the frappe in the system. To provide and interface to the rich admin to keep record of all the attendance attivity.

2.To get the moodle data in frappe , integrating the api in frappe .

3.The api integration work in moodle setting is done by doing the work on webservices and manage protocol.

➡️ **(15-31)-03-23**

1.After complete the moodle work we get problem in frappe interface regarding not getting the required output.

2.Decided to do the work using backend and moodle database.

3.start working on the moodle database .

➡️ **(03-14)-04-23**

1. working on moodle database, tryed lot of sql query t get the table which fulfil the requirement.

2.Decided to create the own query to get the output.
- Check all the tables of moodle database.
- Check attendance ,user, course related table.
- Find the relation and describe the tables.

➡️ **Till Now**

1. Create number of queries but didnot get the output.

2. Check all the database table and start searching the user and their role(editing techer),id,course id,attendance activity,time modified and all.
 
3. Create the sql query:
 
 SELECT   u.id, CONCAT(u.firstname, ' ', u.lastname) AS TeacherName, c.id AS course_id, c.fullname AS course_name , la.target, FROM_UNIXTIME(la.timecreated, '%Y-%m-%d %H:%i:%s') AS Time FROM     mdl_user u JOIN     mdl_role_assignments ra ON ra.userid = u.id JOIN
mdl_context cxt ON cxt.id = ra.contextid JOIN     mdl_course c ON c.id = cxt.instanceid AND c.visible = 1 JOIN     mdl_role r ON r.id = ra.roleid AND r.shortname = 'editingteacher' JOIN mdl_logstore_standard_log la on la.userid = u.id WHERE la.component = "mod_attendance" and la.target != "report" and  u.deleted = 0 ORDER BY     u.lastname,     u.firstname,     c.fullname

4.Getting the output table in database which containing the all needed data.

5.



