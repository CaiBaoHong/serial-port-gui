<template>
  <div class="home">
    <button @click="listSerialPorts">list serial ports</button>
  </div>
</template>

<script>
  const serialport = require('serialport')
  export default {
    name: 'home',
    methods: {
      listSerialPorts() {
        serialport.list((err, ports) => {
          ports.forEach(port => console.log('port: %o', port))
        })
      }
    }
  }
</script>
