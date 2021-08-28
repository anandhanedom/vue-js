<template>
  <div>
    <div>
      <pre>
        {{ JSON.stringify(formValues, null, 2) }}
      </pre>
    </div>
    <form @submit="submitForm">
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" v-model="formValues.name" />
      </div>
      <div>
        <label for="profile">Profile</label>
        <textarea
          type="text"
          id="profile"
          v-model="formValues.profileSummary"
        />
      </div>
      <div>
        <label for="country">Country</label>
        <select id="country" v-model="formValues.country">
          <option value="">Select a country</option>
          <option value="india">India</option>
          <option value="bhutan">Bhutan</option>
          <option value="japan">Japan</option>
          <option value="russia">Russia</option>
        </select>
      </div>
      <div>
        <label for="job-location">Job Location</label>
        <select id="job-location" multiple v-model="formValues.jobLocation">
          <option value="india">India</option>
          <option value="bhutan">Bhutan</option>
          <option value="japan">Japan</option>
          <option value="russia">Russia</option>
        </select>
      </div>
      <div>
        <input
          type="checkbox"
          id="remoteWork"
          v-model="formValues.remoteWork"
          true-value="yes"
          false-value="no"
        />
        <label for="remoteWork">Open to remote work</label>
      </div>

      <div>
        <label>Skill set</label>
        <input
          type="checkbox"
          id="html"
          value="html"
          v-model="formValues.skillSet"
        />
        <label for="html">HTML</label>
        <input
          type="checkbox"
          id="css"
          value="css"
          v-model="formValues.skillSet"
        />
        <label for="css">CSS</label>
        <input
          type="checkbox"
          id="javascript"
          value="javascript"
          v-model="formValues.skillSet"
        />
        <label for="javascript">Javascript</label>
      </div>

      <div>
        <label>Years of experience</label>
        <input
          type="radio"
          id="0-2"
          value="0-2"
          v-model="formValues.yearsOfExperience"
        />
        <label for="0-2">0-2</label>
        <input
          type="radio"
          id="3-5"
          value="3-5"
          v-model="formValues.yearsOfExperience"
        />
        <label for="3-5">3-5</label>
        <input
          type="radio"
          id="6-10"
          value="6-10"
          v-model="formValues.yearsOfExperience"
        />
        <label for="6-10">6-10</label>
      </div>

      <div>
        <button>Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "FormHandling",
  data() {
    return {
      formValues: {
        name: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
        remoteWork: "no",
        skillSet: [],
        yearsOfExperience: "",
      },
    };
  },
  methods: {
    submitForm(e) {
      e.preventDefault();
      console.log(this.formValues);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
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
