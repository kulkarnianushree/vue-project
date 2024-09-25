<template>
    <section>
        <li :key="id">
            <h2>{{ name }}</h2>
            <h3>{{ age }}</h3>
        </li>
    </section>
</template>
<script>
export default {
    props:{
        name:{
            type:String,
            required:true
        },
        age:{
            type:Number,
            required:true
        }
    }
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