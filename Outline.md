# Quizzito Challenge

## 1- Create Vue/cli project
## 2- Design The Page
### Header
* [x] Design Navbar
* [x] Create Navbar Component

### Main content
1. Quizz
* [x] Design Quizz
* [] Create Quizz Component
* [] Extract Quizz Component into Separate Components
    - QuestionBox
    - Question
    - Button
     
2. Book
* [x] Design Book 
* [] Create Book Component
* [] Extract Book Component into Separate Components
    - BookBox
    - BookImage

### Footer
* [x] Design Footer
* [x] Create Footer Component

        
## 3. Make Quizz Working
* [x] Fetch Questions data from api
* [] Change question container Color depending on user answer
    - Green if answer is correct
    - Red if answer is wrong
* [x] Change question container Color when active
    - Background Orange & color white
    - remove class active from all div siblings
    - Remove class active from all choices boxes after
    going to the next question
* [x] Change indicator arrow position dynamically
* [x] Go to next question on button click
    - Increment current property by 1
* [x] Hide Question Box and show user result after complete
    - Render Question box conditionnally if the game has ended
    - increment correctAnswers each time user guesses the right answer
    - Take username from input & bind it in name table cell
    - Display name & result on a table after saving name

**Tasks completed**: 11/16 | 68.75%