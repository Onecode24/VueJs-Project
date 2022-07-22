<template>

 <pre>
    {{JSON.stringify(formValues,null,2)}}
  </pre>
  <form action="" @submit="submitForm">

    <div class="field">
      <label for="name">Name: </label>
      <input type="text" name="name" id="name" v-model.trim.number="formValues.name">
    </div>

    <div class="field">
      <label for="profile">Profile Summary</label>
      <textarea name="profile" id="profile" cols="40" rows="10" v-model.lazy.trim="formValues.profile"></textarea>
    </div>

    <div class="selectField" >
      <label for="country">Country</label>
      <select name="country" id="country" v-model="formValues.country" >
      <option value="">Select a country</option> 
        <option value="Benin">Benin</option>
        <option value="Togo">Togo</option>
        <option value="Nigéria">Nigéria</option>
      </select>
    </div>

    <div class="selectField" >
      <label for="job-location">Job Location</label>
      <select name="job-location" id="job-location" multiple v-model="formValues.joblocation" >
        <option value="Benin">Benin</option>
        <option value="Togo">Togo</option>
        <option value="Nigéria">Nigéria</option>
      </select>
    </div>

    <div class="field checkbox">
      <input type="checkbox" name="remoteWork" id="remote value" v-model="formValues.remoteWork" true-value="yes" false-value="no">
      <label for="remotework">Remote work</label>
    </div>
    <h3>Group check box</h3>
    <div class="group checkbox ">
      <input type="checkbox" value="Html" id="Html" v-model="formValues.skillSet">
      <label for="">HTML</label>
      <input type="checkbox" value="CSS" id="CSS" v-model="formValues.skillSet">
      <label for="">CSS</label>
      <input type="checkbox" value="Javascript" id="Javascript" v-model="formValues.skillSet">
      <label for="">Javascript</label>
    </div> 

     <h3>Choice Radio Box</h3>
    <div class="group checkbox ">
      <input type="radio" value="0-2" id="0-2" v-model="formValues.yearExperience">
      <label for="">0-2</label>
      <input type="radio" value="3-6" id="3-6" v-model="formValues.yearExperience">
      <label for="">3-6</label>
      <input type="radio" value="6-9" id="6-9" v-model="formValues.yearExperience">
      <label for="">6-9</label>
      <input type="radio" value="10+" id="10+" v-model="formValues.yearExperience">
      <label for="">10+</label>
    </div> 

    <div>
      <button type="submit">Submit</button>
    </div>

  </form>
</template>

<script>

export default {
  name: 'App', 
  data(){
    return{
      formValues:{
        name: '',
        profile: '',
        country: '',
        joblocation:[],
        remoteWork: 'no',
        skillSet:[],
        yearExperience: ''
      }
    }
  },

  methods:{
   submitForm(event){
    event.preventDefault()
    console.log('Form Values', this.formValues);
   }
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}
.field, .selectField{
  width: 25%;
  margin-left: 35%;
  margin-top: 20px;
}
label{
  font-size: 20px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
input[type="text"]{
  width: 100%;
  height: 25px;
  border: 1px black solid;
  border-radius: 5px;
  margin-top: 10px;
  margin-left: 0;
}
select{
  margin-left: 25px;
  font-size: 18px;
}
.checkbox{
  text-align: center;
  display: flex;
}
.checkbox > label{
  padding: 0;
  margin: 0;
}
input{
  margin-left: 20px;
}
</style>
