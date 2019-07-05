<template>
  <div>
    <el-col :span="24">
      <h1>{{ title }}</h1>
    </el-col>
    <ul>
      <li v-for="(comment, index) in allcomments" :key="index">
        <el-card :span="12" class="box-card2">
          <div class="pos">
            <p>{{ comment.name }} - {{ comment.position }}</p>
            <p>{{ comment.comment }}</p>
          </div>
        </el-card>
        <br />
      </li>
    </ul>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <span class="test">Leave us a testimonial</span>
      </div>
      <el-form
        :model="myForm"
        :rules="rules"
        ref="myForm"
        label-width="120px"
        class="demo-myForm"
      >
        <div class="half">
          <div class="name">
            <el-form-item prop="name">
              <el-input
                placeholder="Your Name"
                v-model="myForm.name"
              ></el-input>
            </el-form-item>
          </div>
          <div class="title">
            <el-form-item prop="position">
              <el-input
                placeholder="Your Title"
                v-model="myForm.position"
              ></el-input>
            </el-form-item>
          </div>
        </div>
        <el-form-item prop="comment">
          <el-input
            placeholder="Your Comment"
            type="textarea"
            v-model="myForm.comment"
          ></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('myForm')"
            >SUBMIT</el-button
          >
        </el-form-item>
      </el-form>
    </el-card>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      title: "Testimonials",
      allcomments: [],
      myForm: {
        name: "",
        position: "",
        comment: ""
      },
      rules: {
        name: [
          {
            required: true,
            message: "Please input name",
            trigger: "blur"
          },
          {
            max: 50,
            message: "Cannot be more than 50 characters",
            trigger: "blur"
          }
        ],
        position: [
          {
            required: true,
            message: "Please input subject title",
            trigger: "blur"
          },
          {
            max: 50,
            message: "Cannot be more than 50 characters",
            trigger: "blur"
          }
        ],
        comment: [
          {
            required: true,
            message: "Please input comment",
            trigger: "blur"
          },
          {
            max: 120,
            message: "Cannot be more than 120 characters",
            trigger: "blur"
          }
        ]
      }
    };
  },
  methods: {
    // addComment(comment) {
    //   this.user.push(comment);
    //   axios
    //     .put("https://vary0005-midterm.firebaseio.com/data.json", this.comments)
    //     .then(response => {
    //       console.log(response);
    //       console.log("Your data was saved status: " + response.status);
    //     })
    //     .catch(error => {
    //       console.log(error);
    //     });
    // },
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          this.allcomments.push(this.myForm);
          axios
            .put(
              "https://vary0005-midterm.firebaseio.com/data.json",
              this.allcomments
            )
            .then(response => {
              console.log(response);
              console.log("Your data was saved status: " + response.status);
            })
            .catch(error => {
              console.log(error);
            });
        } else {
          // this.dialogVisible = false;
          console.log("error submit!!");
          return false;
        }
      });
    }
  },
  created() {
    axios
      .get("https://vary0005-midterm.firebaseio.com/data.json")
      .then(response => {
        // console.log(response.data);
        if (response.data) {
          // const stuff = JSON.stringify(response.data);
          this.allcomments = response.data;
          console.log(this.allcomments);
        }
      })
      .catch(error => {
        console.log(" there is an error in getting data: " + error.response);
      });
  }
};
</script>

<style>
.name {
  width: 500px;
}

.title {
  width: 500px;
}

.text {
  font-size: 14px;
}

.item {
  margin-bottom: 18px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}
.clearfix:after {
  clear: both;
}

.box-card {
  width: 800px;
  margin: 0 auto;
}

button.el-button {
  float: right;
  width: 300px;
  height: 50px;
  font-size: 1.5rem;
}

.test {
  font-size: 1.5rem;
  float: left;
}

.half {
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: space-between;
}

.pos {
  width: 50%;
  margin: 0 auto;
}

.box-card2 {
  width: 400px;
  margin: 0 auto;
  float: left;
  margin-bottom: 2rem;
  margin-left: 1rem;
  margin-right: 1rem;
  background-color: lightblue;
}

/*div.el-card__body {
  background-color: #c1c1c1;
}*/
</style>
