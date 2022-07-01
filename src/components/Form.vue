<template>
  <div class="wrapper">
    <div class="form" id="form">
      <input @click="isValidFirstName()" type="text" name="FirstName" v-model="formData.firstName" placeholder="First Name">
      <span class="error" v-if="!validFirstName">Invalid first name</span>
      <input @click="isValidLastName()" type="text" name="LastName" v-model="formData.lastName" placeholder="Last Name">
      <span class="error" v-if="!validLastName">Invalid last name</span>
      <input @click="isValidAddress()" type="text" name="Address" v-model="formData.address" placeholder="Address">
      <span class="error" v-if="!validAddress">Invalid address</span>
      <input @click="isValidSSN()" type="text" name="SSN" v-model="formData.ssn" placeholder="SSN">
      <span class="error" v-if="!validSSN">Invalid SSN</span>
    </div>
    <div class="buttons">
      <button @click="reset()" class="btn">Reset</button>
      <button v-if="this.validSSN && this.validAddress && this.validFirstName && this.validLastName" v-on:click="submitData()" class="btn">Save</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "Form",

  data() {
    return {
      formData: {
        firstName: "",
        lastName: "",
        address: "",
        ssn: ""
      },
      validFirstName: false,
      validLastName: false,
      validAddress: false,
      validSSN: false,
      existingssn: []
    }
  },
  methods: {
    isValidFirstName(){
      this.validFirstName = true;
      if (this.formData.firstName === null || this.formData.firstName.trim().length <= 1) {
        this.validFirstName = false;
      }
    },
    isValidLastName(){
      this.validLastName = true;
      if (this.formData.lastName === null || this.formData.lastName.trim().length <= 1) {
        this.validLastName = false;
      }
    },
    isValidAddress(){
      this.validAddress = true;
      if (this.formData.address === null || this.formData.address.trim().length <= 1) {
        this.validAddress = false;
      }
    },
    isValidSSN(){
      this.validSSN = true;
      if (this.formData.ssn === null || !this.formData.ssn.match(/^\d{3}-\d{2}-\d{4}$/) || this.existingssn.includes(this.formData.ssn)) {
        this.validSSN = false;
      }
    },
    async submitData() {
      this.existingssn.push(this.formData.ssn)
      await axios.post("http://localhost:8081/api/members", this.formData)
            .catch(err => console.log(err.message))
    },
    reset () {
      this.formData.firstName = "";
      this.formData.lastName = "";
      this.formData.address = "";
      this.formData.SSN = "";
    }
  },
}
</script>

<style scoped>

::placeholder {
  color: black;
  font-family: Arial,serif;
  font-size: medium;
}

.wrapper{
  margin: 5px;
}

.form{
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}

input{
  border: 2px solid black;
  height: 30px;
  margin-right: 5px;
  margin-left: 5px;

}

.buttons{
  display: flex;
  justify-content: space-around;
  flex-direction: row;
  margin: 3px;
}

.btn {
  border-radius: 50%;
  border: 2px solid black;
  background-color: white;
  width: 50px;
  height: 50px;
}

.error{
  color: red;
  margin: 10px;
}
</style>