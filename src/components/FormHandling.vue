<template>
    <div>
        <h2>----------Form Handling------------</h2>
        <div>
            <pre>
                {{ JSON.stringify(formValues, null, 2) }}
            </pre>
        </div>
        <form @submit.prevent="submitForm">
            <div>
                <label for="name">Name</label>
                <input type="text" name=" " id="name" v-model.trim.lazy="formValues.name">
            </div>
            <div>
                <label for="age">Age</label>
                <input type="number" id="age" v-model.number="formValues.age">
            </div>
            <div>
                <label for="profile">Profile Summary</label>
                <textarea id="profile" v-model="formValues.profileSummary"></textarea>
            </div>
            <div>
                <label for="country">Country</label>
                <select id="country" v-model="formValues.country">
                    <option value="">Select Country</option>
                    <option value="india">India</option>
                    <option value="bangladesh">Bangladesh</option>
                    <option value="pakistan">Pakistan</option>
                </select>
            </div>
            <div>
                <label for="job-location">Job Location</label>
                <select id="job-location" multiple v-model="formValues.jobLocation">
                    <option value="">Select Country</option>
                    <option value="india">India</option>
                    <option value="bangladesh">Bangladesh</option>
                    <option value="pakistan">Pakistan</option>
                </select>                
            </div>
            <div>
                <input type="checkbox" id="remote-work" v-model="formValues.remoteWork" true-value="yes" false-value="no">
                <label for="remote-work">Open to Romote work?</label>
            </div>

            <div>
                <label>Skill Set</label>

                <input type="checkbox" id="html" v-model="formValues.skillSet" value="html">
                <label for="html">HTML</label>

                <input type="checkbox" id="css" v-model="formValues.skillSet" value="css">
                <label for="css">CSS</label>

                <input type="checkbox" id="js" v-model="formValues.skillSet" value="js">
                <label for="js">JS</label>
            </div>

            <div>
                <label>Year of Experience</label>

                <input type="radio" id="0-2" v-model="formValues.yearsOfExperience" value="Fresher">
                <label for="0-2">0-2</label>

                <input type="radio" id="3-10" v-model="formValues.yearsOfExperience" value="Mid">
                <label for="3-10">3-10</label>

                <input type="radio" id="10-10" v-model="formValues.yearsOfExperience" value="Expert">
                <label for="10-10">10-15</label>
            </div>

            <div>
                <button @keyup.enter="submitForm">Submit</button>
            </div>

        </form> 
    </div>


</template>

<script>
export default {
    name: "FormHandling",
    data(){
        return{
            formValues: {
                name: '',
                profileSummary: '',
                country: '',
                jobLocation: [],
                remoteWork: "no",
                skillSet: [],
                yearsOfExperience: '',
                age: null
            }
        }
    },
    methods: {
        submitForm(){
            //event.preventDefault();
            console.log('Form Values: ', this.formValues)
        }
    }
}
</script>

<style>
label{
    font-weight: bold;
    display: flex;
    margin-bottom: 5px;
}
input + label{
    font-weight: bold;
    display: inline-flex;
    margin-right: 20px;
}
input[type='text'],
textarea,
select{
    display: block;
    width: 400px;
    padding: 6px 12px;
    font-size: 14px;
    line-height: 1.428;
    color: #555;
    background-color: #fff;
    background-image: none;
    border: 1px solid #ccc;
    border-radius: 4px;
}
</style>