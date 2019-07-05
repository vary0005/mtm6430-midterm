<template>
  <div>
    <div>
       <el-col :span="24">
        <h1>{{ title }}</h1>
      </el-col>
      <div firstpic>
      <el-row :gutter="20">
        <el-col :span="6">
          <el-image :src="src"></el-image>
        </el-col>
        <el-col :span="6">
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
    <div>
      <el-col :xs="4" :sm="6" :md="8" :xl="4">
        <div class="grid-content bg-purple"></div>
      </el-col> 
      <el-row :gutter="20">
        <el-col :span="6">
          <div class="grid-content bg-purple">
            {{ paragraph }},
            <br />
            <br />
            {{ paragraphh }}
          </div>
        </el-col>
        <el-col :xs="4" :sm="6" :md="8" :xl="11"></el-col>
        <el-col :span="6">
          <el-image :src="src"></el-image>
        </el-col>
      </el-row>
        <div class="grid-content bg-purple"></div>
      </el-col>>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "About the Vue App",
      paragraph:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      paragraphh:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      src:
        "https://loremflickr.com/640/360"
    };
  }
};
</script>

<style scoped lang="scss">

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

.el-row {
  margin-bottom: 20px;
  &:last-child {
    margin-bottom: 0;
  }
}
.el-col {
  border-radius: 4px;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}

.grid-content.bg-purple {
  text-align: left;
}

.grid-content.bg-purple2 {
  text-align: left;
}

div.el-row {
  margin: 0 auto;
  text-align: center;
  float: right;
  padding-left: 15rem;
}
</style>
