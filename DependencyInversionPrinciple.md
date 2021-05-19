# Dependency Inversion Principle-

(Have to edit the file, since I made the notes during the class)

But first, going through-

Reusability and relationship- 

DRP- Donot repeat yourself. Basically, try not to have code duplication in your repo

While looking for code duplication/resuability- 
1. check if the class/method falls in the same family or not
2. Check the commonality and variation 

If everything looks good, we're ready for complete code reuse

In a case of Inheritence/relationship, if we move up to the hiracrchiy, things should get more generalized
And as we move down, we notice vaitations.

Always avoid Inheritance, unnecessarily. 
check- oneway reuse, static relationship

UML- 

The relationship arrow ends at the class with is getting inherited.
Always keep the class as un-instanciable if the class name is in italics.

|- is private
|# is protected
|+ is public

Also, note- abstract class has a protected constructor.

Ripple effect- 
If the base class gets changed, then every class that is inheriting the class will get changed too.
So try your best not to edit/edit carefully the case class.

has-a/uses relationship- is used widely (As compared to is-a)
			- Association, composition, aggregation
			

abstract class UIELement { double height; double width; } 
class Window extends UIElement { string name; method draw()}
class Button extends UIELement { string label; method draw()}
class Textbox extends UIElement { method draw()}
class Label extends UIElement{ string details; method draw()}

class LoginWindow extends Window 
{ Button loginButton;
Button clearButton;
Textbox nameTextbox;
Textbox passworkTextbox;
String usernameLabel;
String passwordLabel;  }   

Association- 
"Belongs to" relationship- uses a referntial attribute to associate one class to another.
			-association needs a third party class to relate the two classes.
			-one to one, many to one, many to many (uses referencial integrity)

Composition- contains/has a relationsip/death relationship
Aggregation - part of/holds

Dependency- 	

Has a relationship- need to identify service providers(low level module) 
and consumer (High level module)

Dependency Inversion - if has a, use interface, not the class itself
		- no direct dependency should be there

# Example for Dependency Injection

//Interface
Iqueue { 
void enqueue(element);
element dequeue();
void clear()
}


//class
CircularQueue implements Iqueue{
enqueue(element){ add element circular }
dequeue() {remove elmenet circular }
clear() { clear} 
}


//class
PriorityQueue implement Iqueue{
enqueu (element) { add element with priority}
dequeue() {remove element with most priority}
clear() {clear}
}


//class
FIFOqueue Implements Iqueue{
enqueue(element) { add element in end}
dequeue() {remove element from start}
clear() {clear}
}


//class
class TaskManager {

Iqueue taskQueue;

TaskManager(Iqueue queue) {
this.taskQueue = queue;
}

manageTask(element){
taskQueue.enqueue(element);
}
}

//class
class TaskScheduler{
Iqueue taskQueue;

TaskScheduler(Iqueue queue) {
this.taskQueue = queue;
}

scheduleTask(){
Element task = taskQueue.dequeue();
return task;
}
}

//Main
main(){
Iqueue circularQueue = new CircularQueue();
TaskManager taskManager = new TaskManager(circularQueue);
taskManager.manageTask(element1);

TaskScheduler taskScheduler = new TaskScheduler(circularQueue);
Element schedule = taskScheduler.scheduleTask();
}
