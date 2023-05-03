Download Link: https://assignmentchef.com/product/solved-cs1331-homework-06-forum-site
<br>
<h1>Problem Description</h1>

It is another hot, sunny morning at Georgia Tech. As you groggily walk to your CS 1331 Lecture, you notice a bizarre, hazy mist in front of your path. Curious, but unfazed, you decide to keep walking, straight into the mist. However, once you step through the other side, the scene entirely changes! Van Leer looks much newer, an entirely different set of students walk around you, and it is now a rainy day. The CULC has mysteriously disappeared from sight. Before long, you realize what has happened: you have been transported to the year 1998! The police would never believe you were from the future, and even if they did, you may be seized and quarantined by the government or scientific community to protect the timeline. No, instead you head over to the nearest library, which fortunately has public computers available for use, and decide to develop your own forum site, to see if any other strangers across the internet have experienced the same bizarre time traveling phenomenon. Later you may try to contact relatives, but right now, this is your top priority. First things first, you must develop a secure backend for your site, and the cornerstone of this backend will be the User class. Equipped with the JDK version 1.1 documented in a textbook from the library and your knowledge of Java from CS 1331, you start working!

<h1>Solution Description</h1>

For this assignment create a file named User.java. In this file, you will be creating a number of fields and methods. Based on the description given for each field and method, you will have to decide whether or not the field/method should be static, and whether it should be private or public.

<strong>Variables:</strong>

<ul>

 <li>String username

  <ul>

   <li>username represents the String name of a given User object. If you create multiple User objects, each should be able to have its own unique username (but note that 2 User objects <em>could </em>have the same username; your code should simply enable 2 User objects to have different usernames if desired). This variable should not be able to be modified outside of the User class.</li>

  </ul></li>

 <li>int password

  <ul>

   <li>password represents the password of a given User object. This variable should be able to be different for different User objects, and it should not be able to be modified outside of the User class (it may be modified within the User class, however).</li>

  </ul></li>

 <li>int numUsers

  <ul>

   <li>numUsers represents the total number of User objects that have been instantiated. This value should be consistent across the User class, only changing when a new User is created. It should not be able to be modified outside of the User class.</li>

  </ul></li>

 <li>User newestUser

  <ul>

   <li>newestUser represents the most recently created User object. It, too, should be consistent across the User class, only being changed when a new User is created. It should not be able to be modified outside of the User class.</li>

   <li>Since there will be no User instances when the program begins, this variable can be set to null by default.</li>

  </ul></li>

 <li>boolean displayNewest

  <ul>

   <li>displayNewest determines the behavior of the method getWelcomeMessage(). It should be the same value across all User objects. It should not be able to be modified outside of the User class, but it will be in its setter setDisplayNewest(boolean displayNewest), which is found within the User class.</li>

   <li>This variable should be set to true by default!</li>

  </ul></li>

</ul>

<strong>The Constructor:</strong>

The constructor should only take in values for username and password and set each of them respectively. numUsers should be incremented, and newestUser should be set to the newest User object created (Hint: what keyword in Java would let us refer to the current User object?).

<strong>The Methods:</strong>

All of the following should be able to be called from outside of the User class. However, some are static, and some are non-static. You must choose the option that makes the most sense.

<ul>

 <li>void setDisplayNewest(boolean displayNewest)

  <ul>

   <li>This method takes in displayNewest and sets the User variable displayNewest to it.</li>

  </ul></li>

 <li>int getNumUsers()

  <ul>

   <li>This method takes no parameters and returns the number of User instances (what variable would give us that?).</li>

  </ul></li>

 <li>String getUsername()

  <ul>

   <li>This method takes no parameters and returns the username of this particular User instance</li>

  </ul></li>

 <li>String getWelcomeMessage()

  <ul>

   <li>This method takes no parameters and returns a String. This method will return a different String message depending on the states of some variables found in the User class.</li>

   <li>If there are currently no User instances, the returned string should match this: “This site doesn’t have any users yet!”</li>

   <li>If there is at least one User instance, and displayNewest is false: “Welcome to our site! We have [numUsers] user(s) and counting!”</li>

   <li>If there is at least one User instance, and displayNewest is true: [newestUsername] just joined our site! Please give them a warm welcome!, where newestUsername is the String username of the newest User.</li>

   <li>Example: “Bob just joined our site! Please give them a warm welcome!”</li>

  </ul></li>

 <li>void changePassword(String usernameInput, int passwordInput, int newPassword)

  <ul>

   <li>This method takes in usernameInput, passwordInput, and newPassword. If usernameInput matches the username of the current User instance, and passwordInput matches the password of the current User instance, then set the current User instance’s password variable equal to newPassword.</li>

  </ul></li>

 <li>boolean validLogin(String usernameInput, int passwordInput)

  <ul>

   <li>This method takes in usernameInput and passwordInput. If usernameInput matches the username of the current User instance, and passwordInput matches the password of the current User instance, return true. Otherwise, return false.</li>

  </ul></li>

</ul>

<strong>Note: Each method requires proper JavaDocs (see below for more information)</strong>

<h1>Testing your code</h1>

If you want to test out your own code before submitting we recommend creating a separate java file and implementing a main method there. You can then create new User objects and test your methods. Below is some sample testing code. <strong>These tests are not comprehensive!</strong>

User.getWelcomeMessage()

-&gt; This site doesn’t have any users yet!

User user1 = new User(“Bob”, 12345);

User.getWelcomeMessage()

-&gt; Bob just joined our site! Please give them a warm welcome! user1.getUsername()

-&gt; Bob

user1.validLogin(“Bob”, 1273)

-&gt; false

User user2 = new User(“Karen”, 456);

User.setDisplayNewest(false);

User.getWelcomeMessage()

-&gt; Welcome to our site! We have 2 user(s) and counting!

Feel free to create your own tests in the main method! Try to write tests for the remaining methods in the file!

<h1>Rubric</h1>

<ul>

 <li>[10] User variables

  <ul>

   <li>[5] Correct usage of static/non-static for each</li>

   <li>[5] Correct visibility for each</li>

  </ul></li>

 <li>[20] Constructor

  <ul>

   <li>[10] Correct setting of username and password</li>

   <li>[5] Increments numUsers</li>

   <li>[5] Updates newestUser</li>

  </ul></li>

 <li>[10] setDisplayNewest

  <ul>

   <li>[5] Correct usage of static/non-static and correct access modifier</li>

   <li>[5] Works as expected</li>

  </ul></li>

 <li>[10] getNumUsers

  <ul>

   <li>[5] Correct usage of static/non-static and correct access modifier</li>

   <li>[5] Works as expected</li>

  </ul></li>

 <li>[10] getUsername

  <ul>

   <li>[5] Correct usage of static/non-static and correct access modifier</li>

   <li>[5] Works as expected</li>

  </ul></li>

 <li>[15] getWelcomeMessage

  <ul>

   <li>[5] Correct usage of static/non-static and correct access modifier</li>

   <li>[5] Works when there are no User instances</li>

   <li>[5] Correctly changes depending on displayNewest</li>

  </ul></li>

 <li>[15] changePassword

  <ul>

   <li>[5] Correct usage of static/non-static and correct access modifier</li>

   <li>[5] Correctly evaluates the input</li>

   <li>[5] Correctly updates the password</li>

  </ul></li>

 <li>[10] validLogin

  <ul>

   <li>[5] Correct usage of static/non-static and correct access modifier <strong>– </strong>[5] Works as expected</li>

  </ul></li>

</ul>

<strong>Allowed Imports</strong>

To prevent trivialization of the assignment, you are <em>not </em>allowed to import any classes or packages.

<h1>Feature Restrictions</h1>

There are a few features and methods in Java that overly simplify the concepts we are trying to teach or break our auto grader. For that reason, do not use any of the following in your final submission:

<ul>

 <li>var (the reserved keyword)</li>

 <li>exit</li>

</ul>

<h1>Javadocs</h1>

For this assignment, you will be commenting your code with Javadocs. Javadocs are a clean and useful way to document your code’s functionality. For more information on what Javadocs are and why they are awesome, the <a href="http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html">online overview</a> for them is extremely detailed and helpful.

You can generate the javadocs for your code using the command below, which will put all the files into a folder called javadoc:

$ javadoc *.java -d javadoc

The relevant tags that you need to include are @author, @version, @param, and @return. Here is an example of a properly Javadoc’d class:

<table width="632">

 <tbody>

  <tr>

   <td width="632"><strong>import </strong>java.util.Scanner;<em>/**</em>* This class represents a Dog object<em>.</em>* <strong>@author </strong>George P<em>. </em>Burdell* <strong>@version </strong><em>1.0</em><em>*/ </em><strong>public class </strong>Dog {<em>/**</em>* Creates an awesome dog <em>(</em>NOT a dawg<em>!)</em><em>*/ </em><strong>public </strong>Dog() { …}<em>/**</em>* This method takes in two ints and returns their sum* <strong>@param a </strong>first number* <strong>@param b </strong>second number <em>* </em><strong>@return </strong>sum of a and b<em>*/ </em><strong>public </strong>int add(int a, int b) {…}}</td>

  </tr>

 </tbody>

</table>

A more thorough tutorial for Javadocs can be found <a href="https://cs1331.gitlab.io/cs1331-style-guide.html">here</a>.

Take note of a few things:

<ol>

 <li>Javadocs are begun with /** and ended with */.</li>

 <li>Every class you write must be Javadoc’d and the @author and @verion tag included. The comments for a class should start with a brief description of the role of the class in your program.</li>

 <li>Every non-private method you write must be Javadoc’d and the @param tag included for every method parameter. The format for an @param tag is @param &lt;name of parameter as written in method header&gt; &lt;description of parameter&gt;. If the method has a non-void return type, include the @return tag which should have a simple description of what the method returns, semantically.</li>

</ol>

Checkstyle can check for Javadocs using the -a flag, as described in the next section.

<h1>Checkstyle</h1>

For this assignment, we will be enforcing style guidelines with Checkstyle, a program we use to check Java style. Checkstyle can be downloaded <a href="https://cs1331.gitlab.io/resources/checkstyle-6.2.2.jar">here</a>.

To run Checkstyle, put the jar file in the same folder as your homework files and run

java -jar checkstyle-6.2.2.jar -a *.java

The Checkstyle cap for this assignment is <strong>25 points</strong>. This means that up to 25 points can be lost from

Checkstyle errors.

<strong>For this homework we will not count off for the checkstyle issue of </strong><strong>“‘username’ hides a field” or </strong><strong>“‘password’ hides a field”</strong>

<h1>Collaboration</h1>

<h2>Collaboration Statement</h2>

To ensure that you acknowledge collaboration and give credit where credit is due, <strong>we require that you place a collaboration statement as a comment at the top of at least one java file that you submit</strong>. That collaboration statement should say either:

<em>I worked on the homework assignment alone, using only course materials. </em>or

<em>In order to help learn course concepts, I worked on the homework with [give the names of the people you worked with], discussed homework topics and issues with [provide names of people], and/or consulted related material that can be found at [cite any other materials not provided as course materials for CS 1331 that assisted your learning].</em>

Recall that comments are special lines in Java that begin with //.

<ul>

 <li></li>

</ul>