# Intelligent Privacy-First Personal Task Management System

A beginner-friendly Java + OOP web project. It includes a task dashboard, create/edit/delete/complete actions, smart rule-based priority recommendations, daily planning suggestions, and a privacy page.

## Technology
- Java 21+ (your JDK 26 can run the project; the build targets Java 21 bytecode)
- Spring Boot, Spring MVC, Thymeleaf
- H2 database (local persistent file database; no separate database installation needed)
- HTML/CSS

## Run in IntelliJ IDEA
1. Extract this ZIP to a folder such as `Documents/IntelligentPrivacyFirstTaskManager`.
2. Open IntelliJ IDEA.
3. Choose **Open**, select the extracted project folder (the folder containing `pom.xml`), and open it.
4. If prompted, choose **Load Maven Project** / **Trust Project**.
5. Wait for Maven dependencies to download. Internet is required the first time.
6. Open `src/main/java/com/taskmanager/TaskManagerApplication.java`.
7. Click the green triangle beside `main`, then **Run 'TaskManagerApplication'**.
8. Open `http://localhost:8080` in your browser.

Alternative: open the IntelliJ Maven tool window, then run `Lifecycle > spring-boot:run`.

## Features included
- Add, edit, delete, and complete tasks
- Deadline, importance, estimated duration, and notes
- Automatic rule-based priority score and recommended next task
- Dashboard summaries for pending, completed, and overdue tasks
- Local H2 database persistence
- Privacy page with safe integration principles
- Integration status placeholders for Gmail and WhatsApp

## Important integration/security notes
Gmail and WhatsApp are **not connected in this starter ZIP**. Real integration requires developer setup, OAuth/API credentials, consent, and provider approval where applicable. This project intentionally does not scrape private chats, read browser sessions, bypass security, or ask for service passwords. The buttons are informational placeholders only.
This is a teaching/demo starter, not a security-audited production system. Before real multi-user deployment, add Spring Security, user ownership/authorization, CSRF review, secure secret management, HTTPS, backups, and security testing.

## Database
H2 stores data in `./data/taskmanager.mv.db` after the application starts. You can inspect the database at `http://localhost:8080/h2-console` while the app is running:
- JDBC URL: `jdbc:h2:file:./data/taskmanager`
- Username: `sa`
- Password: leave blank

## Project structure
```text
src/main/java/com/taskmanager/
  TaskManagerApplication.java
  controller/TaskController.java
  model/Task.java
  model/TaskStatus.java
  service/TaskService.java
  service/PriorityEngine.java
src/main/resources/
  application.properties
  templates/index.html
  templates/task-form.html
  templates/privacy.html
  static/css/style.css
```
