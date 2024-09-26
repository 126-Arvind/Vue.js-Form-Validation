# **📄 Vue.js Form Validation Application**

**✨ Description**

This is a Vue.js application designed to demonstrate form validation in real-time. The form includes fields for Name, Email, and Password, all of which are validated using Vue's Composition API and Computed Properties. It ensures that users provide valid inputs before submitting the form.

**🔍 Preview**
Here’s a quick preview of the form UI:

![image](https://github.com/user-attachments/assets/9602940d-f520-4ebc-be24-9f8b7eb40a85)

**OutPut:** After filling correct details in form
![image](https://github.com/user-attachments/assets/5c8c7cc2-0543-41e2-88c8-23b96601ffb1)


**🔧 Features**

📝 Name Validation: Ensures the Name field is not left empty.

📧 Email Validation: Validates that the email is formatted correctly using a regular expression.

🔒 Password Validation: Ensures that the password is at least 6 characters long.

💬 Live Feedback: Provides real-time feedback to the user about the validity of their inputs.

✅ Form Submission: The form can only be submitted when all fields are valid.

**🛠️ Built With**

Vue.js 3: Modern JavaScript framework for building user interfaces.

HTML5 & CSS3: Used for structuring and styling the form.

JavaScript (ES6): Core logic for form validation.

**🚀 Usage**

**Form Fields:**

Name: Required (cannot be empty).

Email: Must be a valid email format (e.g., example@mail.com).

Password: Must be at least 6 characters long.


**Form Validation:**

Real-time error messages will appear below each input field if the criteria are not met.
The Submit button will be disabled until all fields are correctly filled out.

**Submit the Form:**

Upon successful form submission, the form data is logged to the console.




**📂 Code Structure**

JavaScript: The validation logic for the form is implemented using Vue's Composition API and computed properties to track input values and validate them in real time.


CSS: Custom styles are applied to make the form responsive and visually appealing. Background images, custom buttons, hover states, and error messages enhance the user experience.


**💡 How It Works**

Computed Properties: The validation logic is encapsulated in computed properties that update based on the form data.


Dynamic Error Messages: Error messages dynamically appear under the input fields when the user's input doesn't meet the required criteria.


Submit Button State: The submit button is disabled until all fields are valid.
