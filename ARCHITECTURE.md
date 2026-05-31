PET SERVICE MANAGER – ARCHITECTURE DOCUMENTATION
==================================================

Overview
--------
The Pet Service Manager is a modular, scalable, and role‑secured application designed
for grooming, training, behavior tracking, appointments, service history, marketing,
staff management, reminders, and reporting.

The architecture follows a clean separation of concerns:

• UI Layer (Tkinter Frames)
• Manager/Service Layer (Business Logic)
• Database Layer (SQL Server + migrations)
• Utilities Layer (PDF, images, file handling, logging)
• RBAC + Session Layer (roles, plans, permissions)

This document describes the structure, responsibilities, and interactions of each module.

--------------------------------------------------
1. CORE APPLICATION LAYER
--------------------------------------------------
These files initialize the application, manage routing, and control frame switching.

• main.py
  Entry point of the application.

• app_controller.py
  Central controller that manages UI frames and navigation.

• router.py
  Defines routing rules and maps UI frames to controller actions.

--------------------------------------------------
2. UI FRAMEWORK LAYER
--------------------------------------------------
Reusable UI components and layout helpers.

• ui_main_window.py
  Main Tkinter window wrapper.

• ui_navigation.py
  Navigation helpers and shared UI patterns.

• ui_settings.py
  Application settings UI (admin‑only).

--------------------------------------------------
3. USER & ROLE MANAGEMENT
--------------------------------------------------
Handles authentication, session state, RBAC, and staff management.

• staff_manager_ui.py
  Add/edit/archive staff accounts.

• staff_manager.py
  Staff CRUD operations.

• session_context.py
  Stores session data (user, company, plan, role).

• centralized_rbac.py
  Feature‑level permission enforcement.

Roles:
- Global Admin
- Manager
- Staff

Plans:
- Basic
- Pro
- Enterprise

--------------------------------------------------
4. CORE FEATURE MODULES
--------------------------------------------------

Pets & Owners
-------------
• pets_ui.py
  Pet profiles, grooming notes, behavior notes, training links.

• pets_manager.py
  CRUD operations for pets.

• owners_ui.py
  Owner profiles and contact information.

• owners_manager.py
  CRUD operations for owners.

Appointments
------------
• appointments_ui.py
  Schedule and manage grooming/training appointments.

• appointments_manager.py
  CRUD operations for appointments.

Grooming Notes
--------------
• grooming_notes_ui.py
  Record grooming details and stylist notes.

• grooming_notes_manager.py
  CRUD operations for grooming notes.

Training Progress
-----------------
• training_progress_ui.py
  Log skills, progress levels, and training notes.

Behavior Notes
--------------
• behavior_notes_ui.py
  Track temperament and behavior observations.

• behavior_notes_manager.py
  CRUD operations for behavior notes.

Service History
---------------
• service_history_ui.py
  View and export completed service history.

• service_history_manager.py
  Database operations + PDF export.

Marketing Kits
--------------
• marketing_kit_ui.py
  Generate branded marketing materials.

• marketing_kit_manager.py
  Template and PDF generation logic.

Reminders
---------
• reminders_ui.py
  Task reminders and notifications.

• reminders_manager.py
  CRUD operations for reminders.

Reports
-------
• reports_ui.py
  Financial and operational reporting.

• report_generator.py
  Data aggregation + PDF generation.

--------------------------------------------------
5. DATABASE LAYER
--------------------------------------------------
Handles all database connectivity and schema management.

• db_connection.py
  Centralized SQL Server connection handler.

• db_pet_service_loader.py
  Query execution helper for Pet Service modules.

• database_initializer.py
  Creates initial tables and seeds data.

• database_migrations.py
  Schema updates and versioning.

All managers use parameterized SQL and company_id isolation.

--------------------------------------------------
6. UTILITIES LAYER
--------------------------------------------------
Shared tools used across modules.

• validators.py
  Input validation helpers.

• formatters.py
  Date, currency, and text formatting.

• file_manager.py
  Directory creation, file handling.

• pdf_generator.py
  PDF creation with text blocks and images.

• image_processor.py
  Image resizing and optimization.

• export_import.py
  CSV/JSON import/export utilities.

• logger.py
  Application logging.

--------------------------------------------------
7. ASSETS
--------------------------------------------------
Static resources used by the UI.

• /assets/icons/*
• /assets/images/*
• /assets/templates/*

--------------------------------------------------
8. UI FLOW
--------------------------------------------------
Dashboard →
    Pets
    Owners
    Appointments
    Grooming Notes
    Training Progress
    Behavior Notes
    Service History
    Marketing Kits
    Reminders
    Reports
    Staff Management (Admin only)
    Settings (Admin only)

--------------------------------------------------
9. ARCHITECTURAL PRINCIPLES
--------------------------------------------------

• Separation of Concerns
  UI → Manager → DB

• No SQL in UI
  All database operations live in manager modules or db loader.

• Centralized RBAC
  All feature access controlled by centralized_rbac.py.

• Company Isolation
  Every query includes company_id from session_context.

• Modular UI
  Each feature is a standalone Tkinter Frame.

• PDF‑First Reporting
  All reports exportable via pdf_generator.py.

• Analytics Support
  Charts and summaries integrated into UI and PDFs.

--------------------------------------------------
10. EXTENSIBILITY
--------------------------------------------------
The system supports:

• Adding new modules without modifying core files
• Additional staff roles
• New report types
• External API integrations (future)
• Custom marketing templates
• Expanded appointment types

--------------------------------------------------
11. SUPPORT
--------------------------------------------------
automatinginnovatingai@outlook.com

Thank you for using the Pet Service Manager!
