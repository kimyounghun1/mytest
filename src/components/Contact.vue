<template>
  <div>
    <h1>{{ name }}</h1>
    <h2>{{ phoneNumber }}</h2>
  </div>
</template>

<script>
export default {
  /*name: 'Contact',*/
  props: {
    id:Number,
    name:String,
    phoneNumber:String
  }
}
</script>
