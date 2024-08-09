Learn Git and Github

All Imp. Commands:

- git init
- git status
- git add . 
- git commit -m "add message"
- git config --global user.email "email@gmail.com"
- git config --global user.name "username"
- git log (or) git log --oneline
- git config --global core.editor "code --wait"                        		----------------- changes default editor to vs code
- .gitignore                                                          
- git config --list								------------------ for all configuration info.
  
--------------------------Branching-------------------------------
- git branch                                                        		------------------ list all available branches, default MASTER
- git branch <branch name>                                          		------------------ create branch
- git checkout <branch name>    (or) git switch <branch name>       		------------------ navigate to a particular branch
- git checkout -b <branch name> (or) git switch -c <branch name>    		------------------ create a branch & move there

--------------------------Merging-------------------------------------------
- git merge <branch-name> -m "add message"                          		------------------ merge branch
- git branch -d <branch-name>                 		     	 		------------------ delete branch
- git diff --staged	(or) git diff <id  id>					------------------ compares current version with previous version 									                                                                    of commits on the same file.

-------------------------Stashing---------------------------------------------

- conflicting changes do not allow to switch branch , without commits
- stash stores data temporarily so that you can switch branch even without adding to staging area.
  
- git stash                                  					------------------ you can switch branch
- git stash pop									------------------ bring back those changes
- git stash apply								------------------ apply changes and keep them in stash

-----------------------More Commands-------------------------------------------------------- 

- git checkout <hash> 								------------------ detach head: moves to particular commits
- git checkout master (or) git reflog						------------------ re-attach head: come back to original position
- git rebase master								------------------ never do when u r on master

-----------------------Connecting to GITHUB------------------------------------------------

- how to add SSH key to GitHub 
- connecting to GitHub using SSH key- create & add it

- git remote -v									------------------ to find any remote repository exists
- git branch -M main								------------------ change branch name from MASTER to MAIN
- git remote add origin https://github.com/Guddilivinodkumar/learn-git.git	------------------ establish connection
- git push -u origin main (or) git push --set-upstream origin main 		------------------ pushes to GitHub main branch.
										  	    		-u setup an upstream that allow to run 										   								         future command git push 

----------------------Pull from Remote Repo-------------------------------------------------

- git clone https://github.com/Guddilivinodkumar/learn-git.git			------------------ clone entire repository
- git fetch									------------------ get info but do not put in my work
- git pull 									------------------ (git fetch + git merge)
- git pull origin main								------------------ changes will be merged to main

	GitHub features:-
	 - Adding collaborators
	 - Readme file
	 - markdown format
	 - Adding Gists
	 - code spaces
	 - Dev Container
 
    DOM:-
4.	What is DOM:- DOM represents the content of XML/HTML document as a tree structure. 
5.	DOM is an interface or API , this API can be used with any programming language usually with JS.
6.	It is used to easily access, read and update the content of the document.
7.	
The DOM is a object oriented representation of the web page,  which can be modified with a scripting language such as JavaScript.
8.	Every web browser uses some document object model to make web pages accessible via JavaScript.



Create topic: -
return new NewTopic("foo", 10, (short) 2); 
	
	•  "foo": The name of the topic.
•  10: The number of partitions for the topic.
•  (short) 2: The replication factor, which specifies how many copies of the data will be kept for redundancy.
@KafkaListener: -
	A Kafka listener is a component or a service in an application that consumes messages from an Apache Kafka topic. It acts as a subscriber in a publish-subscribe messaging system, where producers send messages to topics and listeners (or consumers) receive these messages.
Solid principles: -
The SOLID principles are a set of five design principles in object-oriented programming that helps to create more understandable, flexible, and maintainable software. These principles have become fundamental guidelines for designing robust and scalable systems in Java and other object-oriented languages.
1)	Single Responsibility Principle
2)	Open Closed Principle
3)	Liskov substitution Principle
4)	Interface Segregation Principle
5)	Dependency Inversion principle
Single responsibility Principle: -
A class should have one and only one reason to change.
The single responsibility principle states that every java class must perform a single functionality. Implementation of multiple functionalities in a single class mashup the code.
High in cohesion and low is coupling.
Cohesion: - how different software components related to each other
Coupling: - refers to the degree of inter-dependency b/w s/w components.

// Example violating SRP
public class User {
    public void saveToDatabase() {
 // code to save user data to the database
    }
    public void sendEmail() {
        // code to send an email
    }
}
// Refactored to adhere to SRP
public class User {
    // User-related properties and methods
}
public class UserRepository {
    public void saveToDatabase(User user) {
        // code to save user data to the database
    }
}
public class EmailService {
    public void sendEmail(User user) {
        // code to send an email
    }
}

Open/Closed Principle: -
This principle states that according to new requirements the module should be open for extension but closed for modification.
// Example violating OCP
public class Shape {
    public double area() {
        // code for calculating area
    }
}
public class Circle extends Shape {
    public double radius;
}
public class Rectangle extends Shape {
    public double width, height;
}
public class AreaCalculator {
    public double calculateArea(Shape shape) {
        if (shape instanceof Circle) {
            Circle circle = (Circle) shape;
            return Math.PI * circle.radius * circle.radius;
        } else if (shape instanceof Rectangle) {
            Rectangle rectangle = (Rectangle) shape;
            return rectangle.width * rectangle.height;
        }
        return 0;
    }  }
// Refactored to adhere to OCP
public abstract class Shape {
    public abstract double area();
}
public class Circle extends Shape {
    public double radius;
    @Override
    public double area() {
        return Math.PI * radius * radius;
    }
}
public class Rectangle extends Shape {
    public double width, height;
    @Override
    public double area() {
        return width * height;
    }
}
public class AreaCalculator {
    public double calculateArea(Shape shape) {
        return shape.area();
} }
Liskov Substitution Principle: -  
Subtypes must be substitutable for their base types.
It applies to inheritance In such a way that the derived class must be completely substitutable for their base classes. In other words, if class A is a subtype of class B , then we should be able to replace B with A without interrupting the behaviour of the Program.
// Example violating LSP
public class Bird {
    public void fly() {
        // code for flying
    }
}
public class Ostrich extends Bird {
    @Override
    public void fly() {
        // Ostrich can't fly, so this is a problem
        throw new UnsupportedOperationException();
    }
}
// Refactored to adhere to LSP
public abstract class Bird {
    // Common properties and methods for birds
}
public class FlyingBird extends Bird {
    public void fly() {
        // code for flying
    }
}
public class Ostrich extends Bird {
    // Specific properties and methods for ostriches
}
Interface Segregation Principle: -  
The dependency of one class to another one should depend on the smallest possible interface.
. Clients should not be forced to implement interfaces they don’t use.
.Instead of one fat interface many small interfaces are preferred based on groups of methods, each one serving one submodule.
// Example violating ISP
public interface Worker {
    void work();
    void eat();
}
public class HumanWorker implements Worker {
    @Override
    public void work() {
        // code for working
    }
    @Override
    public void eat() {
        // code for eating
    }
}
public class RobotWorker implements Worker {
    @Override
    public void work() {
        // code for working
    }
    @Override
    public void eat() {
        // Robots don't eat, so this is a problem
        throw new UnsupportedOperationException();
    }
}
// Refactored to adhere to ISP
public interface Workable {
    void work();
}
public interface Eatable {
    void eat();
}
public class HumanWorker implements Workable, Eatable {
    @Override
    public void work() {
        // code for working
    }
    @Override
    public void eat() {
        // code for eating
    }
}
public class RobotWorker implements Workable {
    @Override
    public void work() {
        // code for working
    }
}
Dependency Inversion Principle: -   
This principle states that we must use abstraction (abstract class and interfaces) instead of concrete implementations. High-level module should not depend on low level module but both should be depend on the abstraction. 
// Example violating DIP
public class LightBulb {
    public void turnOn() {
        // code to turn on the light bulb
    }
    public void turnOff() {
        // code to turn off the light bulb
    }
}
public class Switch {
    private LightBulb bulb;
public Switch(LightBulb bulb) {
        this.bulb = bulb;
    }
    public void operate() {
        bulb.turnOn();
        // or
        bulb.turnOff();
    }
}
// Refactored to adhere to DIP
public interface Switchable {
    void turnOn();
    void turnOff();
}
public class LightBulb implements Switchable {
    @Override
    public void turnOn() {
        // code to turn on the light bulb
    }

    @Override
    public void turnOff() {
        // code to turn off the light bulb
    }
}
public class Switch {
    private Switchable device;

    public Switch(Switchable device) {
        this.device = device;
    }
    public void operate() {
        device.turnOn();
        // or
        device.turnOff();
    }
}

Equals and HashCode():-
class HelloWorld {
    String str;
    public HelloWorld(String s){
        this.str = s;
    }
    public static void main(String[] args) {

        HelloWorld h = new HelloWorld("Hello1");
        HelloWorld h1 = new HelloWorld("Hello");
        
        System.out.println("Try programiz.pro "+ (h==h1));       // false
        System.out.println("Try programiz.pro "+ (h.equals(h1))); // false 
       System.out.println(h.hashCode()+ " "+h1.hashCode()); // different
        System.out.println("------------------");

        String s = new String("abilash");
        String s1 = new String("abilash");
        String s2 = "abc";
        String s3 = "abc";
        System.out.println("Try programiz.pro "+ (s==s1));      //false
        System.out.println("Try programiz.pro "+ (s.equals(s1)));  //true
        System.out.println("Try programiz.pro "+ (s.hashCode()+" "+s1.hashCode()));								// true
        System.out.println("---------------------");
        
         System.out.println("Try programiz.pro "+ (s2==s3));    // true
        System.out.println("Try programiz.pro "+ (s2.equals(s3)));   //true
        System.out.println("Try programiz.pro "+ (s2.hashCode()+" "+s3.hashCode())); 								// true
    }
}

