<template>
  <v-container>
    <h1 class="title">Get in touch!</h1>

    <v-row justify="center">
      <v-col cols="12" md="6">
        <v-card>
          <v-card-title class="card-h1">Send me a message</v-card-title>
          <v-card-text>
            <v-form ref="contactForm" v-model="valid" @submit.prevent="submitForm">
              <v-text-field
                v-model="form.name"
                label="Name"
                :rules="[v => !!v || 'Name is required']"
                required
              ></v-text-field>

              <v-text-field
                v-model="form.email"
                label="Email"
                :rules="[v => !!v || 'Email is required', v => /.+@.+\..+/.test(v) || 'E-mail must be valid']"
                required
              ></v-text-field>

              <v-text-field
                v-model="form.subject"
                label="Subject"
                :rules="[v => !!v || 'Subject is required']"
                required
              ></v-text-field>

              <v-textarea
                v-model="form.message"
                label="Message"
                :rules="[v => !!v || 'Message is required']"
                required
              ></v-textarea>

              <v-btn
                :disabled="!valid"
                color="#FFEA00"
                @click="submitForm"
                class="mt-4"
              >
                Send Message
              </v-btn>
            </v-form>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <v-snackbar
      v-model="snackbar.visible"
      :color="snackbar.type"
      :timeout="snackbar.timeout"
      bottom
      right
      multi-line
      vertical
    >
      {{ snackbar.message }}
    </v-snackbar>
  </v-container>
</template>

<script>
export default {
  name: 'ContactPage',
  data() {
    return {
      valid: false,
      form: {
        name: '',
        email: '',
        subject: '',
        message: ''
      },
      snackbar: {
        visible: false,
        type: '', 
        message: '',
        timeout: 5000 
      }
    };
  },
  methods: {
    submitForm() {
      if (this.$refs.contactForm.validate()) {
        fetch("https://formspree.io/f/xwpvglwq", {
          method: "POST",
          headers: {
            "Content-Type": "application/json"
          },
          body: JSON.stringify(this.form)
        })
          .then(response => {
            if (response.ok) {
              this.snackbar = {
                visible: true,
                type: "success",
                message: "Message sent successfully!",
                timeout: 5000
              };
              this.$refs.contactForm.reset();
            } else {
              throw new Error("Failed to send message.");
            }
          })
          .catch(error => {
            this.snackbar = {
              visible: true,
              type: "error",
              message: "There was an error sending your message. Please try again later.",
              timeout: 5000
            };
          });
      } else {
        this.snackbar = {
          visible: true,
          type: "error",
          message: "Please correct the errors in the form.",
          timeout: 5000
        };
      }
    }
  }
};
</script>

<style scoped>
.title {
  padding: 18px;
  font-size: 42px;
  font-family: "Lora", serif;
  text-align: center;
  text-decoration: underline #FFEA00;
}
.card-h1 {
  font-size: 28px;
  font-family: "Lora", serif;
  text-align: center;
  margin-bottom: 16px;
}
.v-card {
  border-radius: 10px;
  transition: transform 0.3s, box-shadow 0.3s;
  border: 2px solid #FFEA00;
}
.v-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}
.v-btn {
  color: #FFEA00;
  transition: color 0.3s;
}
.v-btn:hover {
  color: #312d01;
}
.v-btn:focus {
  outline: none;
  box-shadow: 0 0 0 3px rgba(255, 234, 0, 0.5);
}
</style>
