<template>
    <section>
        <form @submit.prevent="formSubmit(userData)">
            <input
                type="name"
                placeholder="Enter Your Name"
                v-model="userData.name"
            />
            <input
                type="number"
                placeholder="Enter Your age"
                v-model="userData.age"
            />
            <button type="submit">Submit</button>
        </form>
    </section>
</template>
<script>
export default {
    // emits:{
    //     "form-submit":function(userData){
    //         if(userData){
    //             return true
    //         }else{
    //             return false
    //         }
    //     }
    // },
    inject:['formSubmit'],
    data:function(){
        return{
            userData:{
                name:'',
                age:''
            }
        }
    },
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  gap: 10px;
  max-width: 300px;
  margin: 0 auto;
}

input {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 10px;
  border: none;
  border-radius: 4px;
  background-color: #007bff;
  color: white;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
</style>
