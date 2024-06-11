<template>
  <div id="app">
    <button v-if="showButton" class="toggle-button" @click="togglePopup">Stil et spørgsmål!</button>
    <div class="popup" :class="{ 'popup-visible': isVisible }">
      <div class="popup-content">
        <h2>Stil os et spørgsmål!</h2>
        <form @submit.prevent="submitForm">
          <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" v-model="email" required />
          </div>
          <div class="form-group">
            <label for="question">Forespørgsel:</label>
            <textarea v-model="question" required></textarea>
          </div>
          <button class="btn-yellow" type="submit">Send</button>
        </form>
        <button class="close-btn" @click="togglePopup">Luk</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isVisible: false,
      showButton: false,
      email: '',
      question: ''
    };
  },
  methods: {
    togglePopup() {
      this.isVisible = !this.isVisible;
    },
    submitForm() {
      // Handle form submission
      alert(`Email: ${this.email}\nQuestion: ${this.question}`);
      this.email = '';
      this.question = '';
      this.togglePopup();
    },
    handleScroll() {
      this.showButton = window.scrollY > 100;
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  }
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}

.toggle-button {
  position: fixed;
  top: 90%;
  right: 0px;
  transform: translateY(-50%);
  padding: 10px 20px;
  background-color: #FCE977;
  color: #1A424B;
  border: none;
  cursor: pointer;
  z-index: 1000;
  font-weight: bold;;
}

.popup {
  position: fixed;
  top: 0;
  right: -300px;
  width: 300px;
  height: 100%;
  background-color: #1A444D;
  box-shadow: -2px 0 5px rgba(0, 0, 0, 0.5);
  transition: right 0.3s ease;
  z-index: 1000;
}

.popup-visible {
  right: 0;
}

.popup-content {
  padding: 20px;
}

.form-group {
  margin-bottom: 15px;
}

.form-group label {
  display: block;
  margin-bottom: 5px;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}

.close-btn {
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  margin-top: 15px;
}

label{
color: white;

}

h2{
color: white;

}
</style>
