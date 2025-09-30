# Product Requirements Document: Single-File Quiz App

## Overall Structure

A self-contained web application delivered as a single HTML file with embedded JavaScript and CSS. The application allows users to upload a JSON file containing quiz questions and then take the quiz with an interactive multiple-choice interface.

**Technical Approach:** Single `.html` file with `<style>` and `<script>` tags containing all CSS and JavaScript inline.

**Key Workflow:**
1. User opens the HTML file in a browser
2. User uploads a `.json` file containing quiz questions
3. Application parses and validates the JSON structure
4. User starts the quiz
5. Questions are presented one at a time with multiple-choice options
6. User selects answers and navigates through questions
7. Application displays final score and results

---

## Core Features/Functionality

### 1. File Upload Interface
- File input element accepting `.json` files
- [Inference] Client-side JSON parsing and validation
- Error handling for invalid JSON or incorrect format
- Preview of loaded quiz metadata (title, number of questions)

### 2. Quiz Question Format
**Expected JSON structure:**
```json
{
  "title": "Quiz Title",
  "questions": [
    {
      "question": "Question text?",
      "options": ["Option A", "Option B", "Option C", "Option D"],
      "correctAnswer": 0
    }
  ]
}
```

### 3. Quiz Interface
- Display one question at a time
- Radio buttons or clickable options for answer selection
- "Next" and "Previous" navigation buttons
- Progress indicator showing current question number
- [Inference] Option to change answers before submission

### 4. Quiz Completion & Results
- Score calculation based on correct answers
- Results screen showing:
  - Total score (correct/total)
  - Percentage
  - [Optional] Review of incorrect answers
- "Restart Quiz" or "Load New Quiz" option

### 5. User Experience Features
- Responsive design for mobile and desktop
- Clear visual feedback for selected answers
- [Inference] Disabled "Next" button until an answer is selected (optional design choice)
- Confirmation before quiz submission

---

## File Structure

### Single HTML File: `quiz-app.html`

**Structure within the file:**

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz App</title>
    
    <style>
        /* All CSS embedded here */
        /* - Layout styles */
        /* - Upload interface styles */
        /* - Quiz interface styles */
        /* - Results screen styles */
        /* - Responsive design rules */
    </style>
</head>
<body>
    <!-- HTML structure here -->
    <!-- - Upload container -->
    <!-- - Quiz container -->
    <!-- - Results container -->
    
    <script>
        /* All JavaScript embedded here */
        /* - File upload handling */
        /* - JSON parsing and validation */
        /* - Quiz state management */
        /* - Navigation logic */
        /* - Score calculation */
        /* - UI rendering functions */
    </script>
</body>
</html>
```

**Component Organization (within the single file):**

1. **HTML Section:**
   - Upload screen container
   - Quiz screen container (initially hidden)
   - Results screen container (initially hidden)

2. **CSS Section:**
   - Global styles and reset
   - Container and layout styles
   - Button and input styles
   - Question and option styles
   - Results display styles
   - Media queries for responsiveness

3. **JavaScript Section:**
   - State management variables (current question, answers, score)
   - File upload event listeners
   - JSON parsing function
   - Quiz initialization function
   - Navigation functions (next/previous)
   - Answer selection handling
   - Score calculation function
   - Screen transition functions
   - DOM manipulation helpers

---