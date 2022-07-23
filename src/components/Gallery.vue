<template>
  <div
    class="modal fade show"
    id="exampleModalFullscreen"
    tabindex="-1"
    aria-labelledby="exampleModalFullscreenLabel"
    style="display: block"
    aria-modal="true"
    role="dialog"
  >
    <div class="modal-dialog modal-fullscreen">
      <div class="modal-content transparent-dark">
        <div class="d-flex justify-content-center h-100 relative">
          <img
            style="object-fit: contain"
            class=""
            :src="require('../assets/img/' + image)"
            alt=""
          />
          <button
            @click="$emit('close')"
            type="button"
            class="btn p-2 transparent-dark rounded-circle position-absolute top-0 end-0 me-5 mt-2"
            aria-label="Close"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="gray"
              width="30"
              height="30"
              viewBox="0 0 320 512"
            >
              <path
                d="M310.6 361.4c12.5 12.5 12.5 32.75 0 45.25C304.4 412.9 296.2 416 288 416s-16.38-3.125-22.62-9.375L160 301.3L54.63 406.6C48.38 412.9 40.19 416 32 416S15.63 412.9 9.375 406.6c-12.5-12.5-12.5-32.75 0-45.25l105.4-105.4L9.375 150.6c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L160 210.8l105.4-105.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-105.4 105.4L310.6 361.4z"
              />
            </svg>
          </button>

          <button
            @click="index--"
            type="button"
            class="btn m-0 transparent-dark rounded-circle p-2 position-absolute translate-middle top-50 start-0 mx-5"
            aria-label="Previous"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="white"
              width="40"
              height="40"
              viewBox="0 0 320 512"
            >
              <path
                d="M224 480c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25l192-192c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25L77.25 256l169.4 169.4c12.5 12.5 12.5 32.75 0 45.25C240.4 476.9 232.2 480 224 480z"
              />
            </svg>
          </button>

          <button
            @click="index++"
            type="button"
            class="btn transparent-dark rounded-circle p-2 position-absolute translate-middle top-50 end-0 mx-3"
            aria-label="Next"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="white"
              width="40"
              height="40"
              viewBox="0 0 320 512"
            >
              -->
              <path
                d="M96 480c-8.188 0-16.38-3.125-22.62-9.375c-12.5-12.5-12.5-32.75 0-45.25L242.8 256L73.38 86.63c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0l192 192c12.5 12.5 12.5 32.75 0 45.25l-192 192C112.4 476.9 104.2 480 96 480z"
              />
            </svg>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Gallery",
  props: {
    images: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      index: 0,
    };
  },
  computed: {
    image() {
      if (this.index < 0) {
        this.index = this.images.length - 1;
      } else if (this.index >= this.images.length) {
        this.index = 0;
      }
      return this.images[this.index];
    },
  },
};
</script>
