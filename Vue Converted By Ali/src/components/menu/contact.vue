<template>
  <div id="menu-4" class="contact content">
    <div class="row">
      <div class="col-md-12">
        <div class="toggle-content text-center spacing">
          <h3>CONTACT US</h3>
          <p>
            Donec mattis enim sit amet nisl faucibus, eu pulvinar nibh facilisis. Aliquam erat volutpat. Vivamus tempus, nisi varius imperdiet molestie, velit mi feugiat felis, sit amet fringilla mi massa sit amet arcu. Mauris dictum nisl id felis lacinia congue. Aliquam lectus nisi, sodales in lacinia quis, lobortis vel sem.
            <br />
            <br />
            <strong>Address:</strong> 123 Thamine Street, Digital Estate, Yangon 10620, Myanmar
            <br />
            <strong>Email:</strong> info@company.com |
            <strong>Tel:</strong>
            010-020-0340
          </p>
        </div>
      </div>

      <div class="col-md-12">
        <div class="contact-form">
          <div class="row">
            <form>
              <fieldset class="col-md-4">
                <input id="name" type="text" placeholder="Name" v-model.lazy="name" />
              </fieldset>
              <fieldset class="col-md-4">
                <input type="email" id="email" placeholder="Email" v-model.lazy="email" />
              </fieldset>
              <fieldset class="col-md-4">
                <input type="text" id="subject" placeholder="Subject" v-model.lazy="subject" />
              </fieldset>
              <fieldset class="col-md-12">
                <textarea id="message" placeholder="Message" v-model.lazy="message"></textarea>
              </fieldset>
              <fieldset class="col-md-12">
                <input
                  type="submit"
                  name="send"
                  value="Send Message"
                  id="submit"
                  class="button"
                  @click.prevent="sendData"
                />
              </fieldset>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      subject: "",
      message: "",
    };
  },
  methods: {
    sendData() {
      alert(
        "Name is " +
          this.name +
          "<> " +
          "Email is " +
          this.email +
          "<> " +
          "Subject is " +
          this.subject +
          "<> " +
          "Msg is " +
          this.message
      );
    },
  },
};
</script>

<style>
</style>