<template>
  <div class="hello">
    <!-- Navbar Start -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">
        <h3><img width="25" src="../assets/quizzito_logo_nerd.png" alt="">كويزيتو</h3>
      </a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">  
          <li class="nav-item">
            <a class="nav-link" href="#">المميزات</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">العملاء</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">المدونة</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">العناوين</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">"للعائلة" <span class="badge badge-primary">new</span></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">"الهدايا"</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              Dropdown
            </a>
            <div class="dropdown-menu" aria-labelledby="navbarDropdown">
              <a class="dropdown-item" href="#">English</a>
              <a class="dropdown-item" href="#">Another action</a>
              <div class="dropdown-divider"></div>
              <a class="dropdown-item" href="#">Something else here</a>
            </div>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <button class="btn btn-danger my-2 my-sm-0" type="submit">Search</button>
          <button class="btn btn-outline-danger my-2 my-sm-0" type="submit">Search</button>
        </form>
      </div>
    </nav>
    <!-- Navbar Start -->
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
