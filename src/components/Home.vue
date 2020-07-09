<template>
<div>
      <header id="home">
         <Navbar />

         <!-- hero -->
         <section class="jumbotron-two">
            <div class="container">
               <div class="row text-center justify-content-center">
               <div id="game" class="col-md-6 col-sm-10 col-10 order-md-2">
               <div v-if="end === false" id="appreciationIndicator" class="d-flex flex-row w-100">
                  <img 
                  v-for="n in 5" :key="n" width="50" alt="score emoji"
                  src="@/assets/emptyemoji.png" 
                  >
               </div>
               <div v-if="end === false" id="progressIndicator">
                  <div id="progressArrow"
                     :style="'left: ' + questions[current].progressArrow"
                  ></div>
               </div>
               <div id="hud"  class="d-none">
                  <div id="hud-item">
                     <p id="progressText" class="hud-prefix">Question</p>
                     <div id="progressBar">
                        <div id="progressBarFull"></div>
                     </div>
                  </div>
                  <div id="hud-item">
                     <p class="hud-prefix">Score</p>
                     <h1 class="hud-main-text" id="score">0</h1>
                  </div>
               </div>
               <!-- Questions Start -->
               <h4 v-if="end === false" id="question" class="pb-2 pt-3" style="direction:rtl;">What is the answer to this questions?</h4>
               <div v-if="end === false" id="questions">
                  <h5>{{questions[current].question}}</h5>
                  <div
                     class="choice-container"
                     @click="selected = 1, linkColor = 'wrong'"
                     :class="{active:selected == 1, wrong: appreciation === 'wrong', correct: appreciation === 'correct'}"
                  >
                     <p class="choice-text" @click="choice= '1'">
                        {{questions[current].choice1}}
                     </p>
                  </div>
                  <div class="choice-container"
                     @click="selected = 2, linkColor = 'wrong'"
                     :class="{active:selected == 2, wrong: appreciation === 'wrong', correct: appreciation === 'correct'}"
                     
                  >
                     <p class="choice-text"  @click="choice= '2'">
                        {{questions[current].choice2}}
                     </p>
                  </div>
                  <div 
                     class="choice-container"
                     @click="selected = 3, linkColor = 'correct', correctAnswers+=10"
                     :class="{active:selected == 3, wrong: appreciation === 'wrong', correct: appreciation === 'correct'}"  
                  >
                     <p class="choice-text" @click="choice= '3'">
                        {{questions[current].choice3}}
                     </p>
                  </div>
               </div>
               <table v-if="end === true" class="table">           
                  <thead>
                     <tr>
                        <th scope="col">#</th>
                        <th scope="col">الاسم</th>
                        <th scope="col">النتيجة</th>
                     </tr>
                  </thead>
               <tbody>
                  <tr>
                     <th scope="row">1</th>
                     <td>-</td>
                     <td>{{correctAnswers}}</td>
                  </tr>
               </tbody>
               </table>
               <!-- Questions end -->
               <div v-if="end === false" class="my-4">
                  <a href="#" class="btn btn-success btn-lg" id="confirm-btn"
                     @click="goNext"
                  >موافق</a>
               </div>
               </div>
               <div id="book" class="card align-center px-1 pb-2 mx-4 rounded col-md-4 col-sm-10 col-10 order-md-1">
                  <div class="card-body">
                     <span class="text-muted mt-1">أنت تلعب الآن ...</span>
                     <h4 class="pb-2">الثعلب والأسد</h4>
                     <img class="w-100 mb-3" src="https://quizzito.com/main/assets/images/quiz/covers/tha3lab.jpg" alt="الثعلب والأسد">
                  </div>
               </div>
            </div>
            </div>
            
         </section>
         <div class="bg-circle"></div>
      </header>

      <Footer />
      
</div>
</template>

<script>
// import EventBus from "../eventBus.js";
import Navbar from "./Navbar";
import Footer from "./Footer";
import questions from "../assets/questions-data.js";

export default {

   name:"home",
   components: {
      Navbar,
      Footer
   },
   data: function() {
      return {
         current: 0,
         end: false,
         choice: null,
         appreciation: '',
         answer: '3',
         questions: questions,
         selected: undefined,
         linkColor: 'default',
         icon: 'emptyemoji.png',
         correctAnswers: 0,
         wrongAnswers: 0,
      }
   },
   methods: {
      goNext: function() {
         if (this.current < 4) {
            this.current += 1;
            this.selected = undefined; // Reset selected answer
         } else {
            this.end = true; // Quizz ended
         }
      },
      checkAnswer: function() {
         if(this.choice === this.answer) {
            this.appreciation = 'correct';
            this.linkColor = 'correct';
            this.icon = 'happyemoji.png';
         } else {
            this.appreciation = 'wrong';
            this.linkColor = 'wrong';
            this.icon = 'sademoji.png'
         }
      },
      // changeIcon: function(event, currentQuestion) {
      //    if (this.current === currentQuestion && this.choice == this.answer) {
      //       this.appreciation = '@/assets/happyemoji.png';
      //       EventBus.$emit("default");
      //    } else if (this.current === currentQuestion && this.choice != this.answer) {
      //       this.appreciation = '@/assets/sademoji.png';
      //       EventBus.$emit("correct");
      //    } else {
      //       this.appreciation = '@/assets/emptyemoji.png';
      //       EventBus.$emit("wrong");
      //    }
      // }
   },
   // watch: {
   //    gameStatus() {
   //       if (this.current === currentQuestion && this.choice == this.answer) {
   //          this.appreciation = '@/assets/happyemoji.png';
   //       } else if (this.current === currentQuestion && this.choice != this.answer) {
   //          this.appreciation = '@/assets/sademoji.png';
   //       } else {
   //          this.appreciation = '@/assets/emptyemoji.png';
   //       }
   //    }
   // }
}
</script>

<style scoped>
#appreciationIndicator {
    padding: 1rem 0;
    position: relative;
    justify-content: space-around;
}
#appreciationIndicator img {
    max-height: 3rem;
    background-size: 0;
    background-position: 50%;
    background-repeat: no-repeat;
    transition: background-size 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.2);
}
#progressIndicator {
    width: 100%;
    height: 5px;
    background-color: orange;
    position: relative;
}
#progressArrow {
    display: block;
    position: absolute;
    border: 15px solid transparent;
    border-bottom: 15px solid orange;
    margin-left: -15px;
    bottom: 0;
    transition: 0.5s left ease-out;
}
.choice-container {
   display: flex;
    margin-bottom: 0.5rem;
    width: 100%;
    font-size: 1.2rem;
    border: 0.1rem solid rgb(86, 165, 235, 0.25);
    background: #fff !important;
    border-radius: 1rem;
}
.default {
   background: #fff !important;
   border-radius: 1rem;
}
.correct {
   background: #080 !important;
}
.wrong {
   background: #f00 !important;
}
.choice-container:hover {
   cursor: pointer;
    transform: translateY(-0.1rem);
    transition: transform 150ms;
    background: rgba(0,0,0,.15) !important;
}
.active {
   color: #fff !important;
   background: orange !important;
}
.choice-text {
   padding: .75em;
    width: 100%;
    margin-bottom: 0;
}
</style>