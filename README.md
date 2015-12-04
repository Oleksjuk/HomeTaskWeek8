#The Idea

Today, you are going to implement simple database storage that stores simple Java objects to database. The main idea is to make it common for any type of Java objects.

So let's make our life easier and simplify few things.
1. Classes that could be stored should be simple and contain only fields of primitive types.
2. They should contain field id that will be used as a table primary key identifier with the same name.
3. All tables should have same simple names as corresponding classes, so class org.geekhub.objects.Cat should corresponds to `cat` table in database.
We will use MySQL database in our application. So, you should download [MySQL Server](https://dev.mysql.com/get/Downloads/MySQLInstaller/mysql-installer-community-5.7.9.1.msi) (direct link for Windows OS, for unix systems you should find it on official website) and install it according to instructions to your computer. For managing your database find and install any MySQL Management Tool you liked. It could be find easily by typing "mysql manager" in Google. Make sure your instance of MySQL Server works fine and your MySQL Management Tool now is your best friend.

#Let's have a fun

1. Download [MySQL JDBC Connector](http://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.37.zip) and add it to [the projects classpath](http://stackoverflow.com/questions/1051640/correct-way-to-add-external-jars-lib-jar-to-an-intellij-idea-project).

2. Download and execute SQL script with your MySQL Management Tool. This script will create database with name geekdb and two tables `user` and `cat`. Make sure you did not modify these tables.

3. Investigate projects code. You may find some errors. Fix them.
Take a look at org.geekhub.objects package. You will find User and Cat classes that reflect data structure for currently created tables. Check Entity class and understand its purposes. Also check well known @Ignore annotation and think maybe we already need to use it for some fields.

4. Take a look at org.geekhub.storage.Storage interface and make sure you understand how it should behave.
Our target is to make one of its implementation that will use database as a storage (MySQL in our case).
I've already started with implementation of DatabaseStorage, but I was so tired to complete it. So you need to implement remaining methods and make it work according to logic described in interface.
Start with prepareEntity and extractResult methods. They will help you with implementation of basic methods.
Some methods already have some code, try to catch the idea and continue implementation. 

5. After you complete with DatabaseStorage switch to Test class. It already has a body and ready to test your assignment.
The only thing that is left for you is to implement createConnection method. It should be pretty simple.
Now you can launch main method in Test class and check the result. If everything is correct you should not get any Exception. If you still have some errors your should analyze and fix them. 

6. As a practice go and create new class that extends Entity with some simple fields and create corresponding table in database. Write some test for new class and realize how it's easy to manipulate with new object types.