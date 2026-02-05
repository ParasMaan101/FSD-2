AIM To design a responsive and interactive User Interface (UI) using Component Libraries such as Material UI and Bootstrap, and to deploy the web application on Netlify using GitHub as a version control platform.

THEORY What is a Component Library? A component library is a collection of pre-built, reusable UI components such as buttons, forms, cards, navigation bars, modals, etc., that help developers build web applications faster and consistently.

Instead of writing everything from scratch in HTML, CSS, and JavaScript, developers can use libraries like:

Material UI (MUI) → For React-based applications

Bootstrap → For responsive web design

Material UI (MUI) Material UI is a popular React UI framework based on Google’s Material Design principles. It provides:

npm -v Step: Create React App Open VS Code terminal and run: npm create vite@latest my-ui-app Choose:

Framework → React

Variant → JavaScript

npm install npm run dev Step 3: Install Material UI Run in VS Code terminal:

npm install @mui/material @emotion/react @emotion/styled Step 4: Create UI Component Create a file ButtonBasic.jsx and add:

jsx Copy code import Button from "@mui/material/Button"; import TextField from "@mui/material/TextField";

export default function ButtonBasic() { return ( <> Click Me </> ); } Import it in App.jsx:

jsx Copy code import ButtonBasic from "./ButtonBasic";

function App() { return (
