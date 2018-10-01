<h1><br /><strong>Java Database Integration Project</strong></h1>
<ul>
<li>A &ldquo;Job Tracking&rdquo; program written in Java - Using Object Oriented Inheritance and Database Connection.<br /><br /></li>
<li>The Code directory contains the 10 classes and Main, which comprise the final program.<br /><br /></li>
<li>The Database Dump directory contains the MySQL Table definitions and insertions to recreate the database. In addition, the database tables can be found as CSV files in the CSVData subdirectory.</li>
</ul>
<p>&nbsp;</p>
<h2><em>This program demonstrates the use of:</em></h2>
<p><span style="text-decoration: underline;"><strong>Database:</strong></span><br /> Utilizes MySQL database connection and dynamically builds SQL statements across as much as three levels of inheritance, allowing modification and deletion of records from database;</p>
<p>Performs verification of user email as simulation of login, immediately identifying which subclass the user is, creating a new object of that type, and placing all relevant fields from the Database into that object to be used as the CurrentUser for the remainder of the session;</p>
<p>Uses the database to police unique email values as well as assign unique user IDs (key);</p>
<p>Retrieves record sets - could easily be enhanced by use of various specific WHERE queries built with user input variables to allow search functionality from Database;</p>
<p><span style="text-decoration: underline;"><strong>Enumeration:</strong></span><br /> Uses Enumeration in both base classes - Person and Posting - to guarantee data integrity within critical fields;</p>
<p>Uses Enumeration within the MySQL Database structure to allow enumerated values to be processed and evaluated properly;</p>
<p><span style="text-decoration: underline;"><strong>Polymorphism:</strong></span><br /> Reads in a RecordSet from database, identifies subtype, builds new object of that type and stores it into an ArrayList of the Base class type;</p>
<p>Iterates through ArrayList and uses overridden .toString to output all elements in the proper format for their individual class.</p>
<p><span style="text-decoration: underline;"><strong>Database class:</strong></span><br /> Allows for cleanliness and modularity of database connection;</p>
<p>Database name, table names, port number, passwords, etc are stored in variables which can be accessed and modified quickly;</p>
<p>Variables are then used to create SQL statement string and create a connection object which is passed;</p>
<p>&nbsp;</p>
<p><span style="text-decoration: underline;"><strong>Inheritance:</strong></span></p>
<p style="padding-left: 30px;"><strong>PERSON</strong>: Abstract Class for all Person Profiles. Contains methods that are overriden in subclasses and chained together to handle each set of fields for the<br /> particular class it is in;</p>
<p style="padding-left: 60px;"><em><strong>EMPLOYER</strong>:</em> Subclass of Person for Profiles of Employers. Allowed to View, Create, Update, and Delete all job Postings; Can Create, Update, and Delete own Profile;</p>
<p style="padding-left: 60px;"><em><strong>APPLICANT</strong>:</em> Abstract Class inheriting from PERSON; all Subclasses of applicant can View job Postings; Can Create, Update, and Delete own Profile;</p>
<p style="padding-left: 90px;"><strong>STUDENT:</strong> Subclass of Applicant; Intended to contain students seeking internships;</p>
<p style="padding-left: 90px;"><strong>REGULAR:</strong> Subclass of Applicant; Intended to contain experienced job seekers;</p>
<p style="padding-left: 30px;">&nbsp;</p>
<p style="padding-left: 30px;"><strong>POSTING:</strong> Abstract class for all Postings;</p>
<p style="padding-left: 60px;"><em><strong>INTERNSHIP:</strong> </em>Subclass of Posting to hold postings related to internships and&nbsp; college students;</p>
<p style="padding-left: 60px;"><em><strong>REGULAR:</strong> </em>Subclass of Posting to hold postings related to experienced job seekers;</p>
<p><span style="text-decoration: underline;">Data Validation and Formatting:</span><br /> All user input, including email addresses, is checked for valid format and/or stripped of special characters before being allowed to be assigned to fields in an attempt to stop possible SQL injection;</p>
<p>Some fields, such as phone number, have output formatted by getter for cleaner output and better user experience;</p>
