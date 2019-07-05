<template>
  <div>
    <div class="hey">
      <el-col :span="24">
        <h1>{{ title }}</h1>
      </el-col>
      <el-row :gutter="20">
        <el-col :span="10">
          <el-image :src="src"></el-image>
        </el-col>
        <el-col :span="14">
          <div class="grid-content bg-purple">
            {{ paragraph }},
            <br />
            <br />
            {{ paragraphh }}
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Welcome to My Vue App",
      paragraph:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      paragraphh:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      src: "https://placebear.com/640/360"
    };
  }
};
</script>

<style>
.hey {
  padding: 2rem;
}

h1 {
  float: left;
}
src {
  border: 10px solid red;
}

.demo-image__placeholder {
  width: 620px; /* you can use % */
  height: auto;
  float: right;
}

.row-bg {
  padding: 2px 0;
}

.grid-content.bg-purple {
  text-align: left;
}
</style>
