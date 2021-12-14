<template>
  <div class="background d-flex flex-wrap justify-content-center align-items-center">
    <div class="col-12 col-md-4 text-center">
      <img class="" src="@/assets/github.png" alt="github-logo">
    </div>
    <div class="col-12 col-md-6 col-lg-7 text-center">
      <h1>GitHub User<br>Search App</h1>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .background {
    background: url("../assets/metalik-dark-blue.jpg") no-repeat center;
    background-size: cover;

      h1 {
        color: rgb(203, 244, 252);
        font-family: 'Raleway', sans-serif;
        font-size: 8rem;
        font-weight: 800;
      }

      img {
        width: 400px;
        height: auto;
      }
  }


  @media (min-width: 300px) {
    .background {
      height: 400px;

      h1 {
        font-size: 2.5rem;
        margin-top: 1rem;
      }
  
      img {
        width: 200px;
      }
    }
  }

  @media (min-width: 576px) {
    .background {

      h1 {
        font-size: 3rem;
        margin-top: 1rem;
      }
  
      img {
        width: 200px;
      }
    }
  }

  @media (min-width: 768px) {
    .background {

      h1 {
        font-size: 4rem;
      }
  
      img {
        width: 230px;
      }
    }
  }

  @media (min-width: 992px) {
    .background {

      h1 {
        font-size: 5rem;
      }
  
      img {
        width: 280px;
      }
    }
  }

  @media (min-width: 1200px) {
    .background {
      height: 500px;

      h1 {
        font-size: 7rem;
      }
  
      img {
        width: 310px;
      }
    }
  }

  @media (min-width: 1400px) {
    .background {
      height: 500px;

      h1 {
        font-size: 8rem;
      }
  
      img {
        width: 350px;
      }
    }
  }
</style>