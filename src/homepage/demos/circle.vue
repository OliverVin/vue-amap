<template>
  <div id="demoComponent" class="demo-component">
      <el-amap id="amap" :zoom="zoom" :center="center">
        <el-amap-circle v-for="circle in circles" :center="circle.center" :radius="circle.radius" :fillOpacity="circle.fillOpacity" :events="circle.events"></el-amap-circle>
      </el-amap>
  </div>
</template>


<script>
export default {
  name: 'demoComponent',
  data() {
    return {
      zoom: 15,
      center: [121.5273285, 31.21515044],
      circles: [
        {
          center: [121.5273285, 31.21515044],
          radius: 200,
          fillOpacity: 0.5,
          events: {
            click: () => {
              alert('click circles');
            },
            init(o) {
              console.log(o);
            }
          }
        }
      ]
    };
  }
};
</script>
