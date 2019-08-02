<template>
  <div id="linebar2" style="width: 100%; height: 300px">
    
  </div>
</template>

<script>
import echarts from 'echarts';
export default {
  name: 'linebar2',
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
        color: ['#3398DB'],
        tooltip : {
            trigger: 'axis',
            axisPointer : {            // 坐标轴指示器，坐标轴触发有效
                type : 'shadow'        // 默认为直线，可选为：'line' | 'shadow'
            }
        },
        grid: {
            left: '3%',
            right: '4%',
            bottom: '3%',
            containLabel: true
        },
        xAxis : [
            {
                type : 'category',
                data : ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
                axisTick: {
                    alignWithLabel: true
                }
            }
        ],
        yAxis : [
            {
                type : 'value'
            }
        ],
        series : [
            {
                name:'直接访问',
                type:'bar',
                barWidth: '60%',
                data:[10, 52, 200, 334, 390, 330, 220]
            },
            {
                name:'直接访问',
                type:'line',
                barWidth: '60%',
                data:[10, 52, 200, 334, 390, 330, 220]
            }
        ]
      }
    }
  },
  methods: {
    draw() {
      console.log(this)
      this.chart = echarts.init(document.getElementById('linebar2'))
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
