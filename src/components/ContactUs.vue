<template>
  <section id="about" class="about">
    <!-- Contact Us button -->
    <button class="contact-btn" @click="toggleForm">Contact Us</button>

    <!-- Contact Form -->
    <div v-if="showForm" class="contact-form" ref="contactForm">
      <!-- Form Header -->
      <div class="form-header">
        <button class="close-btn" @click="closeForm">×</button>
      </div>

      <!-- Form -->
      <form @submit.prevent="submitForm" class="form">
        <p class="form-heading">Get In Touch</p>

        <div class="form-field">
          <input
            required
            placeholder="Name"
            class="input-field"
            type="text"
            v-model="form.name"
          />
        </div>

        <div class="form-field">
          <input
            required
            placeholder="Email"
            class="input-field"
            type="email"
            v-model="form.email"
          />
        </div>

        <div class="form-field">
          <input
            required
            placeholder="Phone Number"
            class="input-field"
            type="text"
            v-model="form.phone"
          />
        </div>

        <div class="form-field">
          <textarea
            required
            placeholder="Message"
            cols="30"
            rows="3"
            class="input-field"
            v-model="form.message"
          ></textarea>
        </div>

        <button type="submit" class="sendMessage-btn">Send Message</button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  name: "ContactUs",
  data() {
    return {
      showForm: false,
      form: {
        name: "",
        email: "",
        phone: "",
        message: "",
      },
    };
  },
  methods: {
    toggleForm() {
      this.showForm = !this.showForm;
    },
    closeForm() {
      this.showForm = false;
    },
    submitForm() {
      const subject = "Contact Us Form Submission";
      const body = `
        Name: ${this.form.name}
        Email: ${this.form.email}
        Phone: ${this.form.phone}
        Message: ${this.form.message}
      `;
      const mailtoLink = `mailto:gowthammrgowthu1999@gmail.com?subject=${encodeURIComponent(
        subject
      )}&body=${encodeURIComponent(body)}`;

      window.location.href = mailtoLink;

      // Reset form fields
      this.form.name = "";
      this.form.email = "";
      this.form.phone = "";
      this.form.message = "";
      this.showForm = false;
    },
    handleClickOutside(event) {
      if (
        this.showForm &&
        !this.$refs.contactForm.contains(event.target) &&
        !event.target.closest(".contact-btn")
      ) {
        this.showForm = false;
      }
    },
  },
  mounted() {
    window.addEventListener("click", this.handleClickOutside);
  },
  beforeUnmount() {
    window.removeEventListener("click", this.handleClickOutside);
  },
};
</script>

<style scoped>
/* General Section Styling */
.about {
  color: #333;
  text-align: center;
  position: relative;
}

/* Contact Button Styling */
.contact-btn {
  background-color: #8acdb2;
  color: white;
  border: none;
  border-radius: 5%;
  padding: 20px;
  font-size: 16px;
  cursor: pointer;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transform: rotate(90deg);
  position: fixed;
  right: -30px;
  bottom: 110px;
  z-index: 15;
}

.contact-btn:hover {
  background-color: #3f82c9;
}

/* Contact Form Styling */
.contact-form {
  position: fixed;
  top: 50%;
  right: 20px;
  transform: translateY(-50%);
  width: 90%;
  max-width: 350px;
  background-color: #171717;
  padding: 1.5rem;
  border-radius: 20px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  z-index: 19;
}

.form-header {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 8px;
  border-bottom: 1px solid #555;
}

.form-header .close-btn {
  background: none;
  border: none;
  color: white;
  font-size: 22px;
  cursor: pointer;
  font-weight: bold;
  transition: color 0.3s ease;
}

.form-header .close-btn:hover {
  color: #ff4d4d;
}

/* Form Styling */
.form {
  display: flex;
  flex-direction: column;
  align-self: center;
  font-family: inherit;
  gap: 10px;
  padding-inline: 2em;
  padding-bottom: 0.4em;
  background-color: #171717;
  border-radius: 20px;
}

.form-heading {
  text-align: center;
  margin: 2em;
  color: #64ffda;
  font-size: 1.2em;
  background-color: transparent;
  align-self: center;
}

.form-field {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5em;
  border-radius: 10px;
  padding: 0.6em;
  border: none;
  outline: none;
  color: white;
  background-color: #171717;
  box-shadow: inset 2px 5px 10px rgb(5, 5, 5);
}

.input-field {
  background: none;
  border: none;
  outline: none;
  width: 100%;
  color: #ccd6f6;
  padding-inline: 1em;
}

.sendMessage-btn {
  cursor: pointer;
  margin-bottom: 3em;
  padding: 1em;
  border-radius: 10px;
  border: none;
  outline: none;
  background-color: transparent;
  color: #64ffda;
  font-weight: bold;
  outline: 1px solid #64ffda;
  transition: all ease-in-out 0.3s;
}

.sendMessage-btn:hover {
  background-color: #64ffda;
  color: #000;
  cursor: pointer;
  box-shadow: inset 2px 5px 10px rgb(5, 5, 5);
}

/* Responsive adjustments for smaller screens */
@media (max-width: 768px) {
  .contact-form {
    top: 15%;
    right: 5%;
    transform: translateY(0);
    width: 90%;
    max-width: 90%;
    padding: 1rem;
  }

  .form-header .close-btn {
    font-size: 20px;
  }
}

@media (max-width: 480px) {
  .contact-form {
    top: 25%;
    width: 95%;
    padding: 0.8rem;
    right: 2.5%;
  }

  .form-group input,
  .form-group textarea {
    padding: 6px;
    font-size: 12px;
  }

  .submit-btn {
    padding: 0.5rem 0.7rem;
    font-size: 14px;
  }
}
</style>
