# User Management Dashboard (MUI Version)

A **React** application for managing users, leveraging **Material-UI (MUI)** for a professional design. This project demonstrates basic **CRUD** (Create, Read, Update, Delete) functionality via the [JSONPlaceholder](https://jsonplaceholder.typicode.com/) mock API.


---

## Table of Contents
1. [Features](#features)
2. [Project Setup](#project-setup)
3. [Directory Structure](#directory-structure)
4. [Components Overview](#components-overview)
5. [Challenges Faced](#challenges-faced)

---

## Features
- **List Users**: Displays users fetched from `jsonplaceholder.typicode.com/users` in a **MUI Table**.
- **Add User**: Opens a **Dialog** to create a new user (simulated).
- **Edit User**: Opens a **Dialog** with user data prefilled, allows updating.
- **Delete User**: Shows a **Confirmation Dialog** before removing the user from the list.
- **Error Handling**: Displays error messages in a **MUI Alert**.
- **Pagination**: Uses Material-UI’s **TablePagination** for client-side pagination.
- **Loading States**: **CircularProgress** spinners appear during API calls and within dialogs.
- **Responsive**: The layout (AppBar, Table, Dialog) adjusts for various screen sizes.

---

## Project Setup

## Clone
  this repository or download the source code:
   ```bash
   git clone https://github.com/your-username/user-management-mui.git
   cd user-management-mui

### Install Dependencies
```bash
npm install
```
This installs React, Material-UI (`@mui/material @mui/icons-material @emotion/react @emotion/styled`), Axios, and other required packages.

### Start the Development Server
```bash
npm start
```
By default, the app launches at [http://localhost:3000](http://localhost:3000).


## Directory Structure
```bash
user-management-mui/
├─ package.json
├─ README.md
└─ src
   ├─ index.js
   ├─ App.js
   ├─ services
   │   └─ userService.js
   └─ components
       ├─ AppBarHeader.js
       ├─ UsersTable.js
       ├─ UserFormDialog.js
       ├─ ConfirmationDialog.js
       └─ ErrorAlert.js
```

### File Overview

#### `index.js`
- Entry point that renders the root React component.

#### `App.js`
- Main container orchestrating the overall logic:
  - Fetches users.
  - Renders `AppBarHeader`, `UsersTable`, and pagination.
  - Manages dialogs for Create/Edit (`UserFormDialog`) and Delete confirmation (`ConfirmationDialog`).

#### `services/userService.js`
- Contains Axios calls to the JSONPlaceholder API for `getUsers`, `createUser`, `updateUser`, and `deleteUser`.

---
## Components Overview

### `UsersTable.js`
- Renders a MUI **Table** (wrapped in `TableContainer`, `Paper`).
- Shows user info: `ID`, `name`, `username`, `email`, `address`, `phone`, `website`, `company`, etc.
- Includes an **Edit (EditIcon)** and **Delete (DeleteIcon)** button for each user row.

### `UserFormDialog.js`
- A **Dialog** for creating or editing a user.
- Fields: `name`, `username`, `email`, `street`, `city`, `phone`, `website`, `company`.
- Basic validation is included for required fields and email format.
- Shows a `CircularProgress` if the form is processing (`formLoading`).

### `ConfirmationDialog.js`
- A **Dialog** for confirming the delete action.
- Displays a custom message (`Are you sure you want to delete...?`).
- Shows a `CircularProgress` in the **Confirm** button if waiting for server response.

### `ErrorAlert.js`
- A **MUI Alert** for errors (e.g., `Error fetching users`).
- Appears at the top of the main container in `App.js`.

---
## Challenges Faced

### 1. Mock API Limitation
- JSONPlaceholder does not persist changes, requiring local state management.

### 2. Material-UI Learning Curve
- Understanding MUI’s table, dialogs, icons, theming, and pagination required thorough documentation study.

### 3. Responsive Layout
- Ensuring the table and dialogs work well on both desktop and mobile screens.

### 4. Validation
- Deciding how much validation to implement and whether to use built-in solutions or external libraries like **Formik/Yup**.
