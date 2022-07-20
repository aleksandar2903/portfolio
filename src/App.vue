<template>
  <div class="sk-cube-container" v-show="isLoading">
    <div class="sk-cube-grid">
      <div class="sk-cube sk-cube1"></div>
      <div class="sk-cube sk-cube2"></div>
      <div class="sk-cube sk-cube3"></div>
      <div class="sk-cube sk-cube4"></div>
      <div class="sk-cube sk-cube5"></div>
      <div class="sk-cube sk-cube6"></div>
      <div class="sk-cube sk-cube7"></div>
      <div class="sk-cube sk-cube8"></div>
      <div class="sk-cube sk-cube9"></div>
    </div>
  </div>
  <nav
    class="navbar navbar-expand-lg navbar-dark fixed-top"
    :class="isScrolling ? 'scrolled' : 'bg-transparent'"
  >
    <div class="container">
      <a class="navbar-brand" href="#"
        ><h2 class="nameLogo">
          <svg
            class="me-1"
            xmlns="http://www.w3.org/2000/svg"
            fill="white"
            width="24"
            viewBox="0 0 576 512"
          >
            <!--! Font Awesome Pro 6.1.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. -->
            <path
              d="M9.372 86.63C-3.124 74.13-3.124 53.87 9.372 41.37C21.87 28.88 42.13 28.88 54.63 41.37L246.6 233.4C259.1 245.9 259.1 266.1 246.6 278.6L54.63 470.6C42.13 483.1 21.87 483.1 9.372 470.6C-3.124 458.1-3.124 437.9 9.372 425.4L178.7 256L9.372 86.63zM544 416C561.7 416 576 430.3 576 448C576 465.7 561.7 480 544 480H256C238.3 480 224 465.7 224 448C224 430.3 238.3 416 256 416H544z"
            />
          </svg>
          Aleksandar <span class="fw-bold"> Stojanović </span>
        </h2></a
      >
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="offcanvas"
        data-bs-target="#offcanvasDarkNavbar"
        aria-controls="offcanvasDarkNavbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="offcanvas offcanvas-end text-bg-dark"
        tabindex="-1"
        id="offcanvasDarkNavbar"
        aria-labelledby="offcanvasDarkNavbarLabel"
      >
        <div class="offcanvas-header">
          <h5 class="offcanvas-title" id="offcanvasDarkNavbarLabel">
            Dark offcanvas
          </h5>
          <button
            type="button"
            class="btn-close btn-close-white"
            data-bs-dismiss="offcanvas"
            aria-label="Close"
          ></button>
        </div>
        <div class="offcanvas-body">
          <ul
            class="navbar-nav justify-content-end align-items-center flex-grow-1 pe-3 gap-5"
          >
            <li class="nav-item">
              <a
                class="h5 navbar-link"
                :class="activeLink === 'home' ? 'active ' : 'text-muted'"
                aria-current="page"
                href="#"
                >Home</a
              >
            </li>
            <li class="nav-item">
              <a
                class="h5 navbar-link"
                :class="activeLink === 'skills' ? 'active ' : 'text-muted'"
                href="#"
                >Skills</a
              >
            </li>
            <li class="nav-item">
              <a
                class="h5 navbar-link"
                :class="activeLink === 'projects' ? 'active' : 'text-muted'"
                href="#"
                >Projects</a
              >
            </li>
          </ul>
          <span class="navbar-text">
            <div class="social-icon">
              <a
                href="https://www.linkedin.com/in/iagoaferreira/"
                target="_blank"
                ><img
                  :src="require('.//assets/img/navLinkedIn.svg')"
                  alt="Linkedin"
              /></a>
              <a href="https://github.com/IagoAntunes" target="_blank"
                ><img
                  :src="require('.//assets/img/navGithub.svg')"
                  alt="Github"
              /></a>
            </div>
            <button class="vvd"><span>Resume</span></button>
          </span>
        </div>
      </div>
    </div>
  </nav>
  <section class="banner" id="home">
    <div class="container">
      <div class="row">
        <div class="col-12 col-md-7">
          <div>
            <span class="tagline">Welcome to my Portfolio</span>
            <h1>
              Hi! I'm
              <span
                class="txt-rotate"
                dataPeriod="1000"
                data-rotate='[ "Web Developer", "Web Designer", "UI/UX Designer" ]'
                ><span class="wrap">{{ text }}</span></span
              >
            </h1>
            <p>
              Computer Science student, future <b>.NET</b> developer currently
              working with mobile development using <b>Xamarin Forms</b>
            </p>

            <button>See my resume</button>
          </div>
          }
        </div>
        <div class="col-12 col-md-5">
          <div>
            <img
              :src="require('.//assets/img/header-img.svg')"
              alt="Header Image"
            />
          </div>
          }
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      isLoading: false,
      active: false,
      isScrolling: false,
      activeLink: "home",
      text: "",
    };
  },
  created() {
    this.isLoading = true;
  },
  async mounted() {
    await new Promise((resolve) => setTimeout(resolve, 2000));
    this.isLoading = false;
    await new Promise((resolve) => setTimeout(resolve, 500));

    window.addEventListener("scroll", this.onScroll);
    this.tick(false);
  },
  methods: {
    onScroll() {
      if (window.scrollY > 50) {
        this.isScrolling = true;
      } else {
        this.isScrolling = false;
      }
    },
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
  watch: {
    done: function () {
      this.writting();
    },
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.onScroll);
  },
};
</script>
