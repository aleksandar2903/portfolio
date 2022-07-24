<template>
  <nav
    class="navbar navbar-expand-xl navbar-dark fixed-top"
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
            <path
              d="M9.372 86.63C-3.124 74.13-3.124 53.87 9.372 41.37C21.87 28.88 42.13 28.88 54.63 41.37L246.6 233.4C259.1 245.9 259.1 266.1 246.6 278.6L54.63 470.6C42.13 483.1 21.87 483.1 9.372 470.6C-3.124 458.1-3.124 437.9 9.372 425.4L178.7 256L9.372 86.63zM544 416C561.7 416 576 430.3 576 448C576 465.7 561.7 480 544 480H256C238.3 480 224 465.7 224 448C224 430.3 238.3 416 256 416H544z"
            />
          </svg>
          <span class="d-none d-sm-inline">Aleksandar</span>
          <span class="fw-bold"> Stojanović </span>
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
        :class="show ? 'show' : ''"
        class="offcanvas offcanvas-end text-bg-dark bg-black"
        tabindex="-1"
        id="offcanvasDarkNavbar"
        :aria-modal="show"
        aria-labelledby="offcanvasDarkNavbarLabel"
        role="dialog"
      >
        <div class="offcanvas-header">
          <a
            class="navbar-brand offcanvas-title"
            id="offcanvasDarkNavbarLabel"
            href="#"
            ><h3 class="nameLogo">
              <svg
                class="me-1"
                xmlns="http://www.w3.org/2000/svg"
                fill="white"
                width="24"
                viewBox="0 0 576 512"
              >
                <path
                  d="M9.372 86.63C-3.124 74.13-3.124 53.87 9.372 41.37C21.87 28.88 42.13 28.88 54.63 41.37L246.6 233.4C259.1 245.9 259.1 266.1 246.6 278.6L54.63 470.6C42.13 483.1 21.87 483.1 9.372 470.6C-3.124 458.1-3.124 437.9 9.372 425.4L178.7 256L9.372 86.63zM544 416C561.7 416 576 430.3 576 448C576 465.7 561.7 480 544 480H256C238.3 480 224 465.7 224 448C224 430.3 238.3 416 256 416H544z"
                />
              </svg>
              Aleksandar <span class="fw-bold"> Stojanović </span>
            </h3></a
          >
          <button
            type="button"
            class="btn-close btn-close-white"
            data-bs-dismiss="offcanvas"
            aria-label="Close"
          ></button>
        </div>
        <div class="offcanvas-body">
          <ul
            class="navbar-nav justify-content-end align-items-center flex-grow-1 pe-xl-3 gap-4 gap-xl-5"
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
                href="#skills"
                >Skills</a
              >
            </li>
            <li class="nav-item">
              <a
                class="h5 navbar-link"
                :class="activeLink === 'projects' ? 'active' : 'text-muted'"
                href="#projects"
                >Projects</a
              >
            </li>
          </ul>
          <div
            class="d-xl-flex ms-xl-4 gap-4 m-0 p-0 align-items-center my-5 my-xl-0"
          >
            <div class="social-icon justify-content-center d-flex gap-2">
              <a
                href="https://www.linkedin.com/in/aleksandar-stojanovic-bb211b224/"
                target="_blank"
                ><img
                  :src="require('../assets/img/navLinkedIn.svg')"
                  alt="Linkedin"
              /></a>
              <a href="https://github.com/aleksandar2903" target="_blank"
                ><img
                  :src="require('../assets/img/navGithub.svg')"
                  alt="Github"
              /></a>
            </div>
            <div class="d-flex">
              <a
                href="https://drive.google.com/file/d/19uabLtjiWWdavqD4CoCWeL06gX3SFtyu/view?usp=sharing"
                target="_blank"
                class="button-transition mx-auto mt-4 mt-xl-0 text-center fw-bold"
              >
                <span>Resume</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isScrolling: false,
      activeLink: "home",
    };
  },
  async mounted() {
    window.addEventListener("scroll", this.onScroll);
  },
  methods: {
    onScroll() {
      if (window.scrollY > 50) {
        this.isScrolling = true;
      } else {
        this.isScrolling = false;
      }
    },
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.onScroll);
  },
};
</script>
