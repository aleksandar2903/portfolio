<template>
  <section class="contact" id="connect">
    <div class="container py-5">
      <div class="row align-items-center">
        <div class="col-md-6">
          <img
            class="updown-animation"
            :src="require('../assets/img/astronaut-footer.svg')"
            alt="Contact Us"
          />
        </div>
        <div class="col-md-6">
          <div>
            <h2>Get In Touch</h2>
            <form
              id="contactform"
              action="https://formsubmit.io/send/07e00902-4c51-41f6-9f3e-1a854e41e403"
              method="POST"
            >
              <div class="row">
                <div class="col-md-6 px-1">
                  <input
                    type="text"
                    placeholder="Text..."
                    name="name"
                    required
                  />
                </div>
                <div class="col-md-6 px-1">
                  <input
                    type="email"
                    placeholder="Email..."
                    name="email"
                    required
                  />
                </div>
                <input
                  name="_formsubmit_id"
                  type="text"
                  style="display: none"
                />
                <div
                  class="col-md-6 px-1 d-flex justify-content-center justify-content-md-start"
                >
                  <button type="submit">Send</button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
    <p class="position-absolute text-center start-50 translate-middle bottom-0">
      Developed by:
      <a
        class="btn btn-link text-white p-0"
        href="https://www.linkedin.com/in/aleksandar-stojanovic-bb211b224/"
        >Aleksandar Stojanović</a
      >
    </p>
  </section>
</template>

<script>
export default {};
</script>

<style></style>
