<template>
  <div>
    <div>
      <pre>
      {{ JSON.stringify(formValues, null, 2) }}
      </pre>
    </div>
    <div>
      <h2 v-once>{{name}}</h2>
      <button @click="name = 'the Best'">Can't change because v-once</button>
    </div>
    <form @submit.prevent="submitForm">
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" v-model.trim.lazy="formValues.name" />
      </div>

      <div>
        <label for="age">Age</label>
        <!-- @keyup.enter="submitForm" -->
        <input type="number" id="age" v-model.number="formValues.age">
      </div>

      <div>
        <label for="profile">Profile Summary</label>
        <textarea id="profile" v-model="formValues.profile" />
      </div>

      <div>
        <label for="country">Country</label>
        <select id="country" v-model="formValues.country">
          <option value="">Select a country</option>
          <option value="India">India</option>
          <option value="Sweden">Sweden</option>
          <option value="UAE">UAE</option>
        </select>
      </div>

      <div>
        <label>Job Location</label>
        <select id="jobLocation" multiple v-model="formValues.jobLocation">
          <option value="">Select your preference</option>
          <option value="India">India</option>
          <option value="Sweden">Sweden</option>
          <option value="UAE">UAE</option>
        </select>
      </div>

      <div>
        <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork">
        <label for="remoteWork">Open for remote work</label>
      </div>

      <div>
        <label>Skill set</label>
        <input type="checkbox" id="html" value="html" v-model="formValues.skillset">
        <label for="html">HTML</label>
        <input type="checkbox" id="css" value="css" v-model="formValues.skillset">
        <label for="css">CSS</label>
        <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillset">
        <label for="html">Javascript</label>
      </div>

      <div>
        <label>Years of Experience</label>
        <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExperience">
        <label for="0-2">0-2</label>
        <input type="radio" id="3-5" value="3-5" v-model="formValues.yearsOfExperience">
        <label for="3-5">3-5</label>
        <input type="radio" id="6-10" value="6-10" v-model="formValues.yearsOfExperience">
        <label for="6-10">6-10</label>
        <input type="radio" id="10+" value="10+" v-model="formValues.yearsOfExperience">
        <label for="10+">10+</label>
      </div>

      <div>
        <button>Submit</button>
      </div>

    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name:"You are great!",
      formValues: {
        name: '',
        profile: '',
        country: '',
        jobLocation: [],
        skillset: [],
        yearsOfExperience: '',
        age: ''
      },
    };
  },
  methods: {
        submitForm(){
          console.log('Form Values', this.formValues);
        }
      }
};
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

label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}

input[type="text"],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
