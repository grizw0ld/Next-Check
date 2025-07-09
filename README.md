Next Check: A Simple Paycheck Planner
Next Check is a sophisticated, state-aware manual budgeting application built with Flutter. It's designed to help users plan their finances from one paycheck to the next with a clean, intuitive, and powerful interface.

Core Features
Template-Based Planning: Set up your recurring incomes, bills, and debts once as templates. Use these templates to instantly generate a detailed financial plan for any upcoming month.

State-Aware Dashboard: The central hub of the application provides a dynamic, at-a-glance view of your financial plans, automatically categorizing months into Active, Upcoming, and Completed sections.

Interactive Monthly Overview: Manage your active month with an interactive workspace. Mark items as paid or received, see your remaining cash update in real-time, and access biller websites directly with integrated hyperlinks.

Seamless Month Rollover: When you close out a month, you can choose to automatically roll over your remaining cash to the next month's plan, creating a seamless financial transition.

Full Data Management: The app includes full Create, Read, Update, and Delete (CRUD) functionality for all your financial templates. Deleting a template archives it (soft delete) to preserve the integrity of your historical data.

Custom Categories: Create and manage your own categories for bills, debts, and incomes, each with a selectable icon for easy visual identification.

Secure Backup & Restore: Your data is yours. Next Check includes a robust, cross-platform backup and restore system. Export your entire database and app state into a single .zip file for safekeeping or to migrate your data to a new device.

Architecture
The application is built on a modern, layered architecture designed for stability and maintainability.

UI Layer (/lib/screens): The user-facing portion of the app, built with Flutter widgets. It contains no direct business logic and delegates all actions to the service layer.

Service Layer (/lib/services): The brain of the application.

Provider: Manages dependency injection and state, ensuring a single, reliable source of truth.

Repositories: Each data type (Bill, Debt, Income) has its own repository that handles all sqflite database queries, completely separating database logic from the UI.

AppState: A dedicated service that manages the status of each month (inProgress, completed, etc.) and persists it to SharedPreferences.

BackupService: A self-contained service that handles the logic of creating and restoring backups.

Data Layer (/lib/models): Defines the shape of the data with simple Dart classes for every object in the app, ensuring data is handled consistently.

Getting Started
To get a local copy up and running, follow these simple steps.

Prerequisites
Flutter SDK: https://flutter.dev/docs/get-started/install
