<template>
  <div class="about space">
    <h1>Are you a robot?</h1>
    <h2>Write in words 3 times the next number:</h2>

    <span>{{ calcResult }}</span>

    <p>
      <input type="password" placeholder="Password" v-model="password" />
    </p>
    <p class="error-message" v-if="password.length < 6">
      The password must be at least 6 characters
    </p>

    <button
      class="btn space"
      :class="changeColor ? 'isGreen' : ''"
      @click="changeColorFunction"
    >
      Enter
    </button>

    <div class="list" v-for="(post, index) in posts" :key="index">
      <ul>
        <li>
          <h3>{{ post.title }}</h3>
          <h5>{{ post.description }}</h5>
          <p>{{ post.content }}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
//iteration 2 A
import { ref } from "vue";
const calcResult = ref(2 + 5);

//iteration 2 B
const stringResult = () => {};

//iteration 3
const password = ref(false);

//iteration 4
const posts = ref([
  {
    title: "Are you really a human?",
    description: "Check your hands",
    content: "The hands can show you a lot of things of your life",
  },
  {
    title: "Are you relly really a human?",
    description: "Check your eyes",
    content: "You can see through someone",
  },
  {
    title: "Left or right?",
    description: "Check your heart",
    content: "This is the end",
  },
]);

//iteration 5

const changeColor = ref(false);
function changeColorFunction() {
  changeColor.value = !changeColor.value;
}
</script>

<style scoped>
.btn,
.email {
  width: 200px;
  height: 40px;
}
.space {
  margin: 30px;
}

p {
  font-size: 16px;
  color: white;
}

.isGreen {
  background-color: green;
}

.about {
  display: flex;
  flex-direction: column;
  padding: 40px;
  align-items: center;
}
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
