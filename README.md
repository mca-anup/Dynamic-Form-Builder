# Dynamic-Form-Builder
Dynamic Form Builder Application that allows users to create custom forms using standard input field types, generate records using the created form, and display the records in a data grid
# MyApp
This project was generated with Angular CLI version 17.3.17.

# 📌 Project Overview
Dynamic Form Builder Application that allows users to:
Build custom forms with configurable fields (Text, Integer, Decimal, TextArea, DateTime, Email, Phone, URL).

Generate dynamic forms based on schema and apply validation rules.
Create and store records using local storage or mock API.
Display records in a grid with search, sorting, and pagination.

# 🏗 Architecture 
Component-based structure

form-builder → add/edit/remove fields

dynamic-form → render schema-driven form

record-list → display submitted records in Material table

# Services

form-schema.service.ts → manages schema state
record.service.ts → manages record storage

# Models

field.model.ts → defines field properties
record.model.ts → defines record structure

# UI

Angular Material for inputs, table, pagination, sorting, and responsive layout

⚙️ Setup Instructions
Clone the repository:

bash
git clone <repo-url>
cd my-app
Install dependencies:

bash
npm install
# Run development server:

# bash
ng serve
Navigate to http://localhost:4200/.

# 📂 Folder Structure
Code
src/app/
  models/
    field.model.ts
    record.model.ts
  services/
    form-schema.service.ts
    record.service.ts
  components/
    form-builder/
    dynamic-form/
    record-list/
# ✅ Assumptions
Records are stored in local storage or in-memory service (no backend integration).

Validation rules are limited to required fields and email format.

Pagination and sorting use Angular Material defaults.

Project is designed for demo purposes; production-ready features (auth, API, DB) are out of scope.

# 📸 Demo (Optional)
Include screenshots or a short video showing:

Form Builder panel

Dynamic Form rendering

Record Grid with search, sort, pagination

# 🔧 Development server
Run ng serve for a dev server. Navigate to http://localhost:4200/. The application will automatically reload if you change any of the source files.

# 🛠 Code scaffolding
Run ng generate component component-name to generate a new component. You can also use ng generate directive|pipe|service|class|guard|interface|enum|module.

# 📦 Build
Run ng build to build the project. The build artifacts will be stored in the dist/ directory.

# Running unit tests
Run ng test to execute the unit tests via Karma.

🔍 Running end-to-end tests
Run ng e2e to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

📖 Further help
To get more help on the Angular CLI use ng help or go check out the Angular CLI Overview and Command Reference page.

# Flow is 
Save
 ↓
dynamicForm.submit()
 ↓
form validation
 ↓
RecordService.addRecord()
 ↓
recordsSubject.next()
 ↓
RecordListComponent receives records
 ↓
MatTable updates
 ↓
Dialog closes

BETTER ARCHITECTURE
                   Form Builder
                       │
                       ▼
               FormSchemaService
                       │
                       ▼
                 Dynamic Form
                       │
                       ▼
                RecordService
                       │
                 records$
                       │
                       ▼
                Record List
                       │
                       ▼
                  MatTable
This is much better for the assignment because it demonstrates proper state management and avoids having two different sources of truth.
