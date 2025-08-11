<template>
  <div class="block">
    click me
    {{ delay }}
  </div>
</template>

<script>
export default {
 props:["delay"]
}
</script>

<style>
    .block{
        width: 400px;
        border-radius: 20px;
        background-color: black;
        color: #fff;
        padding: 100px 0;
        text-align: center;
        margin:40px auto;
    }
</style>