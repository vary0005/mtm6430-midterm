<template>
  <div id="app">
    <el-menu
      :default-active="activeIndex"
      class="el-menu-demo"
      mode="horizontal"
      @select="handleSelect"
    ></el-menu>
    <div id="nav">
      <div class="line"></div>
      <el-menu
        :default-active="activeIndex2"
        class="el-menu-demo"
        mode="horizontal"
        @select="handleSelect"
        background-color="lightblue"
        text-color="#fff"
        active-text-color="#000000"
      >
        <div class="myvue">
          <h1>{{ title }}</h1>
        </div>
        <el-menu-item index="1">
          <router-link :to="{ name: 'home' }">Home</router-link>
        </el-menu-item>
        <el-menu-item index="2">
          <router-link :to="{ name: 'about' }">About</router-link>
        </el-menu-item>
        <el-menu-item index="3">
          <router-link :to="{ name: 'contact' }">Contact</router-link>
        </el-menu-item>
        <el-menu-item index="4">
          <router-link :to="{ name: 'user' }">Testimonials</router-link>
        </el-menu-item>
      </el-menu>
    </div>
    <footer>{{ copy }}</footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      copy: "Copyrights @Jasmine Vary",
      title: "My Vue App",
      activeIndex: "1",
      activeIndex2: "1"
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    }
  }
};
</script>

<style>
h1 {
  color: #ffd04b;
}

a {
  font-size: 1.2rem;
}

.myvue h1 {
  color: white;
  padding-left: 18rem;
  padding-right: 3rem;
}

footer {
  padding: 25px;
  width: 100%;
  position: absolute;
  background-color: lightblue;
  bottom: 0;
  color: white;
  font-size: 1.2rem;
}
</style>
