<template>
    <!-- Navbar Start -->
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
    <!-- Navbar End -->
</template>

<script>
export default {
  name: 'Navbar',
}
</script>