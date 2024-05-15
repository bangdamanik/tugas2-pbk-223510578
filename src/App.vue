<template>
  <div id="app">
    <h1 class="header" :style="headerStyle">Selamat Datang Lae ku</h1>
    <p :class="{'highlight': isHighlighted}" @mouseover="toggleHighlight" @mouseleave="toggleHighlight">
      Bulir Mouse ketulisan ini
    </p>
    <input type="text" v-model="userInput" placeholder="Type something..." />
    <button @click="submitInput">Submit</button>
    <p v-if="submittedText">You submitted: {{ submittedText }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userInput: '',
      submittedText: '',
      isHighlighted: false,
    };
  },
  computed: {
    headerStyle() {
      return {
        color: this.isHighlighted ? 'blue' : 'black',
        fontSize: '2em',
        textDecoration: this.isHighlighted ? 'underline' : 'none'
      };
    }
  },
  methods: {
    toggleHighlight() {
      this.isHighlighted = !this.isHighlighted;
    },
    submitInput() {
      this.submittedText = this.userInput;
      this.userInput = '';
    }
  }
};
</script>

<style scoped>
.header {
  text-align: center;
  margin-bottom: 20px;
}

.highlight {
  background-color: blue;
}

p{
  color: azure;
}
</style>