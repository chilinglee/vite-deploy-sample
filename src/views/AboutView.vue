<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
  <div>
    {{data}}
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
<script>
  export default {
    data(){
      return{
        data:{}
      }
    },
    mounted(){
      const path = import.meta.env.VITE_PATH;
      console.log(import.meta.env.VITE_TEXT);
      this.$http.get(path).
        then(({data})=>{
          this.data = data.results[0];
        }).catch((err) => {
          //console.dir(err);
        });
    }
  }
</script>
