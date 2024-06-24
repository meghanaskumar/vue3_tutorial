<template>
  <GreetMan name="hioooooooooooo"/>
<form @submit="submitForm">
  <div>
    <h2>{{ fullname }}</h2>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
  <div>
    <label for="name">Name</label>
    <input type="text" id="name" v-model.trim="formValues.name">
  </div>
  <div>
    <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
    <label for="remoteWork">Remote Work</label>
  </div>
  <div>
    <label for="skill-set">Skill Set</label>
    <input type="checkbox" id="html" value="html" v-model="formValues.skillSet">
    <label for="html">HTML</label>
    <input type="checkbox" id="css" value="css" v-model="formValues.skillSet">
    <label for="css">css</label>
    <input type="checkbox" id="php" value="php" v-model="formValues.skillSet">
    <label for="php">php</label>
  </div>
  <button type="submit">submit</button>
</form>
</template>


<script>

import GreetMan from './components/GreetMan.vue'
export default{
  name: "App",
  components:{
    GreetMan,
  },
  data() {
    return {
      formValues: {
        name: '',
        remoteWork: 'no',
        age:0,
        skillSet:[],
  },
  
  first:'kkkkkkk',
        last:'mmmmmmmmmm',
    }
  },
  methods: {
    submitForm(event) {
      event.preventDefault()
      console.log(this.formValues);

    }
  },
  computed: {
    fullname() {
      return `${this.first} ${this.last}`
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  font-style: italic;
  text-decoration: underline;
}
.danger{
  color: red;
}
.headersize{
  font-size: 40;
}
.orange{
  color: orange;
}
.success{
  color: green;
}
.promoted{
  font-style: italic;
}
.new{
  color: green;
}
.sold-out{
  color: brown;
}
</style>
