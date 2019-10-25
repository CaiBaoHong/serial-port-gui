<template>
  <div class="home">
    <button @click="listSerialPorts">list serial ports</button>
    <div>ports:</div>
    <div>{{ports}}</div>
  </div>
</template>

<script>
  const serialport = require('serialport')
  export default {
    name: 'home',
    data(){
      return {
        ports: ['empty']
      }
    },
    methods: {
      listSerialPorts() {
        serialport.list((err, ports) => {
          if (ports.length===0){
            this.ports = ['empty']
          }else{
            this.ports = ports
          }
        })
      }
    }
  }
</script>