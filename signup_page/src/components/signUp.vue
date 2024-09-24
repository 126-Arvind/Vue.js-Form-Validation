<script setup>
import {ref , computed} from 'vue'

const formData = ref({
    name: '',
    email: '',
    password: ''
})

const isNameValid = computed(()=> formData.value.name.trim() !== '')
const isEmailValid = computed(() =>
  /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(formData.value.email)
);
const isPasswordValid = computed(()=> formData.value.password.length >=6)

const isformValid = computed(()=> isNameValid.value && isEmailValid.value && isPasswordValid.value)

const submitForm =()=>{
    if (isformValid.value){
        console.log('From submitted', formData.value)
    } else{
        console.log('Form is invalid. Please checked once ')
    }
}



</script>

<template>
<h1>Form Validation</h1>
  <div>
    <form @submit.prevent="submitForm" class="custom-form">
        <div class="form-group">
            <label for="name">Name:</label>
            <input v-model="formData.name" type="text" id="name" placeholder="Enter your name here.....">
            <span v-if="!isNameValid" class="error">Name is required</span>
        </div>
      
        <div class="form-group">
            <label for="name">Email:</label>
            <input v-model="formData.email" type="email" id="email" placeholder="Enter your email-id here.....">
            <span v-if="!isEmailValid" class="error">Please enter a valid email <address></address></span>
        </div>
      
        <div class="form-group">
            <label for="password">Password:</label>
            <input v-model="formData.password" type="password" id="password" placeholder="Enter your password here....."> 
            <span v-if="!isPasswordValid" class="error">Password must be at least 6 character</span>
        </div>
      <button tyoe="submit" :disabled="!isformValid" class="submit-button">Submit</button>
    </form>
  </div>
</template>

<style scoped>
/* Custom form styles */
.custom-form {
  min-width: 350px;
  margin: 40px auto;
  padding: 20px;
  background: url('../assets/back.webp') no-repeat center center/cover;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(173, 20, 20, 0.1);
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

/* Form Group Styling */
.form-group {
  margin-bottom: 25px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

/* Label Styling */
label {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 8px;
  color: black;
  text-align: left; /* Align text to the left */
  width: 100%; /* Ensures label spans full width */
}

/* Input Styling */
input {
  width: 92%;
  padding: 12px 15px;
  font-size: 15px;
  border: 1px solid #ccc;
  border-radius: 6px;
  background-color: #fff;
  transition: border-color 0.3s ease;
}

input:focus {
  border-color: #3498db;
  outline: none;
}

/* Error Message Styling */
.error {
  color: red;
  font-size: 14px;
  margin-top: 6px;
  font-style: italic;
  text-align: left; /* Align error text to the left */
  width: 100%; /* Ensures error spans full width */
}

/* Submit Button Styling */
.submit-button {
  width: 100%;
  padding: 12px;
  font-size: 18px;
  font-weight: bold;
  background-color: #030301;
  color: #fff;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.submit-button:hover {
  background-color: #e93903da;
}

.submit-button:disabled {
  background-color: #e93903da;
  cursor: not-allowed;
}

/* Add some hover and focus effects */
input:hover, input:focus {
  border-color: #2980b9;
}

/* Form container styling */
div {
  text-align: center;
}

/* Form Heading */
h1 {
  color: #e93903da;
  font-size: 35px;
  margin-bottom: 20px;
  text-transform: uppercase;
  text-align: center;
}
</style>
