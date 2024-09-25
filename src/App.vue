<template>
     <header>
        <h1>My App</h1>
     </header>  
     <section>
        <ul>
            <active-user 
                v-for="user in userList"
                :key="user.id"
                :id="user.id"
                :name="user.name"
                :age="user.age"
            ></active-user>
        </ul>
     </section>   
     <section>
        <user-data @form-submit="submitHandler"></user-data>
     </section>                                                                                                                                                                       
</template>

<script>
export default {
    data:function(){
        return{
            userList:[]
        }
    },
    methods:{
        submitHandler(user){
            this.userList.push(user)
            console.log(this.userList)
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
