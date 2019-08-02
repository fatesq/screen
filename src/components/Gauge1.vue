<template>
  <div id="gauge" style="width: 100%; height: 200px">
    
  </div>
</template>

<script>
import echarts from 'echarts';
export default {
  name: 'gauge',
  data() {
    return {
      chart: null
    }
  },
  mounted() {
    this.draw()
  },
  computed: {
    options() {
      return {
        tooltip : {
            formatter: "{a} <br/>{b} : {c}%"
        },
        series: [
            {
                name: '业务指标',
                type: 'gauge',
                detail: {formatter:'{value}%'},
                data: [{value: 50, name: '完成率'}]
            }
        ]
      }
    }
  },
  methods: {
    draw() {
      console.log(this)
      this.chart = echarts.init(document.getElementById('gauge'))
      this.chart.setOption(this.options)
      window.addEventListener('resize', ()=> {
        this.chart.resize();
      })
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">

</style>
