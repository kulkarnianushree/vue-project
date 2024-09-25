<template>
     <header>
        <h1>My App</h1>
     </header>  
     <section>
        <ul>
            <active-user></active-user>
        </ul>
     </section>   
     <section>
        <user-data ></user-data>
     </section>                                                                                                                                                                       
</template>

<script>
export default {
    data:function(){
        return{
            userList:[]
        }
    },
    provide:function () {
      return{
        userList:this.userList,
        formSubmit:this.submitHandler
      }
    },
    methods:{
        submitHandler(user){
            this.userList.push(user)
        }
    }
}
</script>

<style scoped>
header {
  text-align: center;
  margin-bottom: 20px;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 20px;
  padding: 0 20px;
}

.user-list {
  flex: 1;
  max-width: 60%;
}

.user-form {
  flex: 1;
  max-width: 40%;
}

ul {
  list-style-type: none;
  padding: 0;
}

section {
  margin: 20px;
}

@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
</style>
