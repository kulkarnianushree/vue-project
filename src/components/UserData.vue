<template>
    <section>
        <form @submit.prevent="formSubmit">
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
    emits:{
        "form-submit":function(userData){
            if(userData){
                return true
            }else{
                return false
            }
        }
    },
    data:function(){
        return{
            userData:{
                name:'',
                age:''
            }
        }
    },
    methods:{
        formSubmit(){
            this.$emit('form-submit',{
                ...this.userData,
                id:Math.random().toString()
            })
            this.userData.name = '',
            this.userData.age=''
        }
    }
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
