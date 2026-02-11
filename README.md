import java.util.ArrayList;
import java.util.Scanner;
public class ToDoList {
private ArrayList<Task> tasks;
private Scanner scanner;
public ToDoList() {
tasks = new ArrayList<>();
scanner = new Scanner(System.in);
}
public void displayMenu() {
System.out.println("\nTo-Do List Menu:");
System.out.println("1. Add Task");
System.out.println("2. View Tasks");
System.out.println("3. Remove Task");
System.out.println("4. Mark Task as Done");
System.out.println("5. Exit");
System.out.print("Choose an option: ");
}
public void addTask() {
System.out.print("Enter a new task: ");
String taskDescription = scanner.nextLine();
tasks.add(new Task(taskDescription));
System.out.println("Task added: " + taskDescription);
}
public void viewTasks() {
if (tasks.isEmpty()) {
System.out.println("No tasks available.");
} else {
System.out.println("Tasks:");
for (int i = 0; i < tasks.size(); i++) {
Task task = tasks.get(i);lnñ p
System.out.println((i + 1) + ". [" + (task.isDone() ? "X" : " ") + "] " +
task.getDescription());
}
}
}
public void removeTask() {
viewTasks();
if (!tasks.isEmpty()) {
System.out.print("Enter the task number to remove: ");
