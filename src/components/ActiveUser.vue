<template>
    <section>
        <li 
            v-for='user in userList'
            :key="user.id">
            <h2>{{ user.name }}</h2>
            <h3>{{ user.age }}</h3>
        </li>
    </section>
</template>
<script>
export default {
    inject:['userList']
}
</script>

<style scoped>
li {
  background-color: #f9f9f9;
  padding: 10px;
  margin-bottom: 10px;
  border-radius: 5px;
}

h2 {
  margin: 0;
  font-size: 18px;
  color: #333;
}

h3 {
  margin: 0;
  font-size: 14px;
  color: orange;
}
</style>