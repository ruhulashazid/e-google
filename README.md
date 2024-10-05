
# Project Plan

## Tech Stack:
- **Frontend**: HTML, CSS, Vite, TypeScript
- **Backend**: Node.js (Express)
- **Database**: MongoDB (local)
- **Authentication**: Firebase

---

## **Day 1-2: Initial Setup**
- **Goal**: Set up the base structure of the project.
- **Tasks**:
  1. Create a new project structure for both front-end and back-end using **Vite** and **Node.js**.
  2. Set up **Firebase** for authentication.
  3. Set up local **MongoDB** instance.
  4. Install necessary dependencies (Express, TypeScript, Firebase SDK, Mongoose, etc.).
  5. Initialize Git repository for version control.

### Setup Code Example:
```bash
# Install dependencies
npm install express mongoose firebase-admin vite typescript

# Setup Vite project
npm init vite@latest

# Setup Express server
npm install express

# Initialize TypeScript config
npx tsc --init

# Firebase setup
npm install firebase-admin
```

- **Deliverables**:
  - Basic project skeleton.
  - Connected Firebase Authentication and MongoDB.

---

## **Day 3-5: Authentication with Firebase**
- **Goal**: Implement user sign-up, login, and authentication.
- **Tasks**:
  1. Implement Firebase authentication for sign-up, login, and logout.
  2. Create routes for protecting form creation and viewing.
  3. Secure front-end and back-end communication with Firebase tokens.

- **Deliverables**:
  - Working authentication (sign-up, login).
  - Secure routes for form management.

---

## **Day 6-9: Form Builder UI**
- **Goal**: Implement the form builder allowing users to drag and drop elements.
- **Tasks**:
  1. Design the form builder interface with **HTML/CSS**.
  2. Implement drag-and-drop functionality to add form fields like text, multiple choice, checkboxes.
  3. Use TypeScript to manage the dynamic state of the form fields.
  4. Add validation to ensure fields are properly configured before saving.

### Example Shortcut Code for Form Builder Logic:
```typescript
// Typescript code for dynamic form field state management
interface FormField {
  type: string;
  label: string;
  options?: string[];
  required: boolean;
}

const formFields: FormField[] = [];

function addField(field: FormField) {
  formFields.push(field);
}

// Drag and drop logic for adding fields dynamically
function handleDrop(event: DragEvent) {
  const field = extractFieldFromEvent(event); 
  addField(field);
}

```

- **Deliverables**:
  - A fully working form builder UI.
  - Drag-and-drop support for form creation.

---

## **Day 10-11: Form Submission**
- **Goal**: Allow users to fill out and submit created forms.
- **Tasks**:
  1. Implement a form viewer for users to fill out forms.
  2. Handle form input validation.
  3. Store submitted form data in MongoDB.

---

## **Day 12-14: Response Management Dashboard**
- **Goal**: Build a dashboard for form creators to view responses.
- **Tasks**:
  1. Create a dashboard to show all created forms and their responses.
  2. Allow form creators to view collected data in a tabular format.
  3. Add sorting and filtering options for responses (e.g., by date).

---

## **Day 15: Conditional Logic Implementation**
- **Goal**: Implement basic conditional logic in the form builder.
- **Tasks**:
  1. Add UI to allow users to define conditional logic (e.g., show/hide fields based on answers).
  2. Implement the logic to dynamically show/hide fields in the form viewer.

### Example Shortcut Code for Conditional Logic:
```typescript
// Example logic for showing/hiding fields
function handleFieldChange(response: any, fieldId: string) {
  const field = formFields.find(f => f.id === fieldId);
  if (field) {
    field.hidden = shouldHideField(response, field);
  }
}

function shouldHideField(response: any, field: FormField) {
  // Logic to hide/show based on response
  return response === 'some condition';
}
```

---

## **Day 16: Data Export (CSV/Excel)**
- **Goal**: Allow users to export form responses.
- **Tasks**:
  1. Implement utility functions to convert form responses into CSV or Excel format.
  2. Add export options to the response dashboard.

---

## **Day 17-18: Testing and Debugging**
- **Goal**: Test all core functionalities and fix bugs.
- **Tasks**:
  1. Unit test key functionalities (form builder, submissions, dashboard).
  2. Debug any performance or security issues.
  3. Ensure all API endpoints work properly and handle errors gracefully.

---

## **Day 19-20: Final Deployment**
- **Goal**: Deploy the project on a live server.
- **Tasks**:
  1. Deploy front-end (Vercel or Netlify) and back-end (Heroku or DigitalOcean).
  2. Configure environment variables for Firebase and MongoDB.
  3. Perform final checks on the deployed version.

- **Deliverables**:
  - Fully deployed application.

