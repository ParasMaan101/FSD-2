# Experiment 6: Form Validation with Material-UI

This experiment demonstrates how to build a validated login form using Material-UI components and React state management to handle form validation.

## Project Overview

A practical implementation of form handling with client-side validation using Material-UI components (TextField, Button, Container) combined with React's useState hook for state management.

## File Structure

```
src/
├─ App.jsx
└─ main.jsx
```

## Key Concepts

### useState Hook
- Stores form field values (email, password)
- Maintains error state for validation messages
- Updates state on user input

### Form Validation
- Custom `validate()` function checks email format and password length
- Sets error messages based on validation rules
- Returns boolean to control form submission

### Material-UI Components
- **TextField**: Customizable input field with error styling and helper text
- **Button**: Submit button with Material-UI styling
- **Container**: Responsive layout wrapper
- **Typography**: Heading text with Material-UI variants

### Error Handling
- `error` prop displays red outline when validation fails
- `helperText` prop shows validation error messages below field

## Working Code

**App.jsx**
```jsx
import { TextField, Button, Container, Typography } from '@mui/material';
import { useState } from 'react';

function App() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [errors, setErrors] = useState({});

  const validate = () => {
    let temp = {};
    if(!email.includes('@'))
      temp.email = 'Invalid email';
    if(password.length < 6)
      temp.password = 'Min 6 characters';

    setErrors(temp);
    return Object.keys(temp).length === 0;
  }

  const handleSubmit = (e) => {
    e.preventDefault();
    if(validate())
      alert('Form submitted successfully');
  }

  return (
    <Container maxWidth="sm">
      <Typography variant="h5" gutterBottom>Login Form</Typography>

      <form onSubmit={handleSubmit}>

      <TextField
        fullWidth
        margin="normal"
        label="Email"
        value={email}
        onChange={e => setEmail(e.target.value)}
        error={Boolean(errors.email)}
        helperText={errors.email}
      />

      <TextField
        fullWidth
        margin="normal"
        type="password"
        label="Password"
        value={password}
        onChange={e => setPassword(e.target.value)}
        error={Boolean(errors.password)}
        helperText={errors.password}
      />

      <Button
        variant="contained"
        type="submit"
      >Login</Button>

      </form>
    </Container>
  );
}

export default App;
```

## Learning Outcomes

1. **Master Form State Management**: Learn how to use React's useState hook to manage form input values and error states, enabling real-time form control and validation feedback.

2. **Implement Client-Side Validation**: Understand how to validate form inputs on the client side with custom validation logic for email format and password requirements before submission.

3. **Integrate Material-UI Components**: Discover how to use Material-UI's pre-built components (TextField, Button, Container, Typography) to create professional-looking forms with minimal styling effort.

4. **Handle Form Submission and Error Display**: Learn to prevent default form submission, validate inputs, and display user-friendly error messages using Material-UI's built-in error styling and helper text features.

## Getting Started

```bash
npm create vite@latest exp6-forms -- --template react
cd exp6-forms
npm install
npm install @mui/material @emotion/react @emotion/styled
npm run dev
```

The application will start on `http://localhost:5173` by default.

## Installation Notes

Make sure to install all Material-UI dependencies:
```bash
npm install @mui/material @emotion/react @emotion/styled
```

The `@emotion/react` and `@emotion/styled` packages are peer dependencies required by Material-UI for styling.
