<template>
  <div id="app">
    <transition name="fade">
      <h1 v-if="isClicked" class="heading1">BAU-YA</h1>
    </transition>
    <button type="button" @click="onClick">切り替え</button>
    <ul class="list">
      <TheCreator
        v-for="creator in creators"
        :key="creator.name"
        :name="creator.name"
        :age="creator.age"
        :job="creator.job"
      />
    </ul>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
import TheCreator from "@/components/TheCreator";

export default {
  components: {
    TheCreator
  },
  data() {
    return {
      isClicked: false,
      creators: [
        {
          name: "沖 良矢",
          age: 38,
          job: "インタラクションデザイナー"
        },
        {
          name: "生明 義秀",
          age: 52,
          job: "デザイナー"
        },
        {
          name: "宮田 優希",
          age: 33,
          job: "Webデザイナー"
        }
      ]
    };
  },
  methods: {
    onClick() {
      this.isClicked = !this.isClicked;
    }
  }
};
</script>

<style lang="scss" scoped>
.fade-enter-active {
  transition: opacity 1s ease-out;
}

.fade-enter {
  opacity: 0;
}

.heading1 {
  font-size: 100px;
  color: red;
}

.list {
  display: flex;
  justify-content: center;
  list-style: none;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
