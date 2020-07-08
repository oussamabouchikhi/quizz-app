<template>
<div>
      <header id="home">
         <!-- navbar -->
         <nav class="navbar navbar-expand-lg navbar-light bg-light cf-8377-area-26063">
            <div class="container">
               <a class="navbar-brand" href="https://quizzito.com/main/">
                  <h3 class="gradient-mask"><img width="50" src="https://quizzito.com/main/assets/images/quizzito_logo_nerd.png" alt="Quizzito Symbol">كويزيتو</h3>
               </a>
               <div class="d-inline-flex align-items-center justify-content-between">
                  <a href="https://api.whatsapp.com/send?phone=41765085874&amp;text=كوزيتو! هل يمكن أن تخبرني أكثر؟" class="mx-3" target="_blank" onclick="gtag('event', 'whatsapp', { 'event_category': 'conversion', 'event_label': 'singup'});"> <img class="whatslogo d-block d-lg-none d-xl-none" src="https://quizzito.com/main/assets/images/whats.png" alt="What's App Logo"> </a>
                  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#site-nav" aria-controls="site-nav" aria-expanded="false" aria-label="Toggle navigation">
                  <span class="navbar-toggler-icon"></span>
                  </button>
               </div>
               <div class="collapse navbar-collapse" id="site-nav">
                  <ul class="navbar-nav text-sm-left mr-auto">
                     <li class="nav-item">
                        <a class="nav-link" href="https://quizzito.com/main/#features" >المميزات</a>
                     </li>
                     <li class="nav-item">
                        <a class="nav-link" href="https://quizzito.com/main/#pricing"  >العملاء</a>
                     </li>
                     <li class="nav-item">
                        <a class="nav-link" href="https://blog.quizzito.com/" target="_blank"  >المدونة</a>
                     </li>
                     <li class="nav-item">
                        <a class="nav-link" href="https://blog.quizzito.com/2019/10/20/classification-kids-book/" target="_blank"  >العناوين</a>
                     </li>
                     <li class="nav-item">
                        <a class="nav-link" href="https://family.quizzito.com/" target="_blank" >للعائلة <span class="badge badge-primary">جديد</span></a>
                     </li>
                     <li class="nav-item">
                        <a class="nav-link" href="https://quizzito.com/main/quizzito/reward">الهدايا</a>
                     </li>
                     <li class="nav-item text-center">
                        <a id="login_teacher" href="#" class="btn align-middle btn-outline-primary my-2 my-lg-0">الدخول</a>
                     </li>
                     <li class="nav-item text-center">
                        <a href="https://quizzito.com/main/quizzito/join" class="btn align-middle btn-primary my-2 my-lg-0" target="_blank">التسجيل</a>
                     </li>
                     <li class="nav-item dropdown language-switch">
                        <a class="nav-link" href="#" data-toggle="dropdown"><span class="pe-7s-global"></span>  عربي <span class="pe-2x pe-7s-angle-down"></span>  </a>
                        <div class="dropdown-menu">
                           <a class="dropdown-item" href="https://quizzito.com/main/language/change/english">English</a>
                           <a class="dropdown-item" href="https://quizzito.com/main/language/change/french">Français</a>
                        </div>
                     </li>
                     <li class="nav-item d-none d-lg-block d-xl-block">
                        <a href="https://api.whatsapp.com/send?phone=41765085874&amp;text=كوزيتو! هل يمكن أن تخبرني أكثر؟" target="_blank" class="ml-2" onclick="gtag('event', 'whatsapp', { 'event_category': 'conversion', 'event_label': 'singup'});"> <img width="30" class="whatslogo" src="https://quizzito.com/main/assets/images/whats.png" alt="What's App Logo"> </a>
                     </li>
                  </ul>
               </div>
            </div>
         </nav>
         <!-- // end navbar -->

         <!-- hero -->
         <section class="jumbotron-two">
            <div class="container">
               <div class="row text-center justify-content-center">
               <div id="game" class="col-md-6 col-sm-10 col-10 order-md-2">
               <div id="appreciationIndicator" class="d-flex flex-row w-100">
                  <img 
                     v-for="n in 5" :key="n" 
                     width="50" src="../assets/emptyemoji.png" alt="score emoji">
               </div>
               <div id="progressIndicator">
                  <div id="progressArrow"></div>
               </div>
               <div id="hud" class="d-none">
                  <div id="hud-item">
                     <p id="progressText" class="hud-prefix">
                     Question
                     </p>
                     <div id="progressBar">
                        <div id="progressBarFull"></div>
                     </div>

                  </div>
                  <div id="hud-item">
                     <p class="hud-prefix">
                     Score
                     </p>
                     <h1 class="hud-main-text" id="score">
                     0
                     </h1>
                  </div>
               </div>
               <h4 id="question" class="pb-2 pt-3" style="direction:rtl;">What is the answer to this questions?</h4>
               <div class="choice-container">
                  <p class="choice-text" data-number="1">Choice 1</p>
               </div>
               <div class="choice-container">
                  <p class="choice-text" data-number="2">Choice 2</p>
               </div>
               <div class="choice-container">
                  <p class="choice-text" data-number="3">Choice 3</p>
               </div>
               <div class="my-4">
                  <a href="#" class="btn btn-success btn-lg" id="confirm-btn">موافق</a>
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
            <!-- <div class="row align-items-center text-center">
               <div id="end" class="col-sm-12">
                  <span class="text-muted">النتيجة النهائية</span>
                  <h1 id="finalScore"></h1>
                  
                  <form class="d-flex justify-content-center mb-5">
                     <input
                        type="text"
                        name="username"
                        class="form-control" style="width:auto;"
                        id="username"
                        placeholder="اكتب اسمك هنا"
                        />
                     <button
                        class="btn btn-primary btn-xl mx-2 my-lg-0"
                        id="saveScoreBtn"
                        onclick="saveHighScore(event)"
                        disabled
                        >
                     حفظ</button>
                  </form>
                  <hr>
                  <a href="https://quizzito.com/main/quizzito/tryquiz" class="btn btn-xl btn-outline-primary"  onClick="gtag('event', 'try_another_quiz', { 'event_category': 'engagement', 'event_label': 'quiz'});">جرب كويزاً آخر</a>
                  <a href="https://quizzito.com/main/quizzito/join" class="btn btn-xl btn-primary" target="_blank"  onClick="gtag('event', 'signup_after_quiz', { 'event_category': 'engagement', 'event_label': 'quiz'});">التسجيل</a>
               </div>
            </div> -->
            </div>
            
         </section>
         <!-- <div class="bg-circle"></div> -->
      </header>
      
      <footer>
         <div class="section bg-light mt-4" id="footer">
        <div class="container text-center">
            <div class="row">
                <div class="col-sm-4 footer-cta">
                    <h3>كويزيتو</h3>
                    <p class="mt-3 ml-1 text-muted">إقرأ .. إلعب واربح</p>
                    <p class="ml-1"><a class="btn btn-primary" href="https://quizzito.com/main/quizzito/join" target="_blank" onClick="gtag('event', 'signup_bottom', { 'event_category': 'conversion', 'event_label': 'singup'});">أطلب الآن →</a></p>
                    <!-- <p class="mt-3 ml-1"> <a class="btn btn-sm btn-outline-primary" href="#"> Around the World </a></p> -->
                    <!-- // end .lead -->
                </div>
                <!-- // end .col-sm-3 -->
                <div class="col-sm-2">
                    <ul class="list-unstyled footer-links ml-1 px-0">
                        <li>
                            <b> كن معنا </b>
                        </li>
                        <li>
                            <a href="https://docs.google.com/forms/u/0/d/1Hm2XiFNGMIdXyBzNhGHH9eLbKaT7k854Qch6HG-Z8I4/edit" target="_blank">
                                 شريكا                            </a>
                        </li>
                        <li>
                            <a href="https://docs.google.com/forms/u/0/d/1Kypyzg7myBvPAp7dLthUgMqBLTxMT4Mz5jyL9ExBFVQ/edit" target="_blank">
                                 راعيا                            </a>
                        </li>
                        <li>
                            <a href="https://docs.google.com/forms/d/18n8dIGb61py5W6duAvAdaOGCn12E63biHlHzOdHOUlY/edit" target="_blank">
                                بائعا                             </a>
                        </li>
                    </ul>
                </div>
                <!-- // end .col-sm-3 -->

                <div class="col-sm-2">
                    <ul class="list-unstyled footer-links ml-1 px-0">
                        <li>
                            <b> الإجتماعي </b>
                        </li>
                        <li><a href="https://web.facebook.com/QuizzitoApp/" target="_blank">Facebook</a></li>
                        <li><a href="https://twitter.com/quizzitoapp/" target="_blank">Twitter</a></li>
                        <li><a href="https://www.youtube.com/watch?v=Lg-ZGpXAFnQ" target="_blank"  >Youtube</a></li>
                        <li><a target = "_blank" href="https://www.instagram.com/quizzitoapp/">Instagram</a></li>
                    </ul>
                </div>
                <!-- // end .col-sm-3 -->
                <div class="col-sm-2">
                    <ul class="list-unstyled footer-links ml-1 px-0">
                        <li>
                            <b> روابط أخرى </b>
                        </li>
                        <li>
                            <a href="https://quizzito.com/main/quizzito/other/terms_of_use/ar" target="_blank">
                                شروط الإستخدام                            </a>
                        </li>
                        <li>
                            <a href="https://quizzito.com/main/quizzito/other/privacy_policy/ar" target="_blank">
                                الخصوصية                            </a>
                        </li>
                    </ul>
                </div>
                <!-- // end .col-sm-3 -->
                <div class="col-sm-2">
                    <a href="#home" class="btn btn-sm btn-outline-primary ml-1">إلى الأعلى</a>
                </div>
                <!-- // end .col-sm-3 -->
            </div>
            <!-- // end .row -->
            <div class="text-center mt-4">
            </div>
            <div class="row mt-4 small justify-content-md-center" dir="ltr"><div class="col-md-auto">
    </div><div class="col-md-auto">  <i class="pe-7s-mail-open-file px-2"></i>  info@quizzito.com
    </div>
    </div>
    <div class="row mt-2"><div class="col text-muted small text-center">
        نشكر كل عملائنا على ثقتهم بما نقدمه    </div></div>


        </div>
        <!-- // end .container -->
    </div>
      </footer>
      
      
</div>
</template>

<script>


export default {
    name:"home",
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
.choice-container:hover {
   cursor: pointer;
    transform: translateY(-0.1rem);
    transition: transform 150ms;
    background: rgba(0,0,0,.15) !important;
}
.choice-text {
   padding: .75em;
    width: 100%;
    margin-bottom: 0;
}
</style>