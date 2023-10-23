<template>
  <Main/>
</template>

<script>
import Main from './components/Main.vue'
import fs from 'fs'
import { app } from '@electron/remote'


export default {
  name: 'App',
  components: {
    Main
  },
  mounted(){
    console.log("APP PATH", app.getAppPath());
    console.log("Mounted...");
    const files = fs.readdirSync(app.getPath('appData'));
    console.log("GOT FILES", files)
    files.forEach((file)=>{
      console.log(file);
    })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
