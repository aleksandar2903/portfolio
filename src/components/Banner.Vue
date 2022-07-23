<template>
  <section class="banner" id="home">
    <div class="container">
      <div class="row">
        <div class="col-12 col-md-7">
          <div>
            <div class="m-0 d-flex">
              <h1>Hi!</h1>
              <h1 class="leftright-animation">&#128075;</h1>
            </div>
            <h1>
              I'm
              <span class="txt-rotate"
                ><span class="wrap">{{ text }}</span></span
              >
            </h1>
            <p class="h4">
              Student of the Faculty of Science and Mathematics, future
              <b class="text-light">.NET</b> developer currently working with
              desktop, mobile and web development using
              <b class="text-light">UWP</b>,
              <b class="text-light">Xamarin Forms</b>,
              <b class="text-light">ASP.NET Core</b> and
              <b class="text-light">Vue.js</b>
            </p>

            <a
              target="_blank"
              href="https://drive.google.com/file/d/19uabLtjiWWdavqD4CoCWeL06gX3SFtyu/view?usp=sharing"
            >
              See my resume
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 16 16"
                width="25"
                height="25"
                fill="currentColor"
              >
                <path
                  fill-rule="evenodd"
                  d="M1 8a7 7 0 1 0 14 0A7 7 0 0 0 1 8zm15 0A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM4.5 7.5a.5.5 0 0 0 0 1h5.793l-2.147 2.146a.5.5 0 0 0 .708.708l3-3a.5.5 0 0 0 0-.708l-3-3a.5.5 0 1 0-.708.708L10.293 7.5H4.5z"
                ></path>
              </svg>
            </a>
          </div>
        </div>
        <div class="col-12 col-md-5 updown-animation">
          <img
            class="w-100 m-auto"
            :src="require('../assets/img/astronaut-header.svg')"
            alt="Astronaut Header Image"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      text: "",
    };
  },
  mounted() {
    this.tick(false);
  },
  methods: {
    tick(isDeleting) {
      let text = ".NET Developer ";
      text.split("").forEach((element, i) =>
        setTimeout(() => {
          if (isDeleting) {
            this.text = this.text.slice(0, text.length - i - 1);
          } else {
            this.text += element;
          }
          if (i === text.length - 1) {
            this.tick(!isDeleting);
          }
        }, i * 200)
      );
    },
  },
};
</script>
