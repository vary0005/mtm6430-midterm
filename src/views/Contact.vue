<template>
  <div>
    <el-col :span="24">
      <h1>{{ title }}</h1>
    </el-col>

    <el-row :span="12" :gutter="10">
      <el-col :xs="4" :sm="6" :md="8" :lg="9" :xl="11">
        <div class="div1">
          <h3>{{ hours }}</h3>
          <p>
            {{ address1 }}
            <br />
            {{ address2 }}
            <br />
            {{ phonen }}
          </p>
        </div>
      </el-col>
      <el-col :xs="4" :sm="6" :md="8" :lg="9" :xl="11">
        <div class="div2">
          <h3>{{ hours }}</h3>
          <ul>
            <li v-for="obj of operation">{{ obj.key }} : {{ obj.value }}</li>
          </ul>
        </div>
      </el-col>
      <el-col :xs="8" :sm="6" :md="4" :lg="3" :xl="1">
        <div class="grid-content bg-purple-light"></div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Contact",
      address1: "1385 Woodroffe Ave",
      address2: "Nepean, ON K2G 1V8",
      phonen: "(613) 727-4723",
      hours: "Hours of Operation",
      add: "Address",
      operation: [
        {
          key: "Monday",
          value: "8:00am-4:00pm"
        },
        {
          key: "Tuesday",
          value: "8:00am-4:00pm"
        },
        {
          key: "Wednesday",
          value: "8:00am-4:00pm"
        },
        {
          key: "Thursday",
          value: "8:00am-4:00pm"
        },
        {
          key: "Friday",
          value: "8:00am-4:00pm"
        },
        {
          key: "Saturday",
          value: "8:00am-4:00pm"
        },
        {
          key: "Sunday",
          value: "Closed"
        }
      ]
    };
  }
};
</script>

<style>
li {
  list-style: none;
  font-size: 1.2rem;
}
p {
  font-size: 1.2rem;
}

.div1 {
  padding-left: 30rem;
  text-align: left;
}

.div2 {
  text-align: left;
}
</style>
