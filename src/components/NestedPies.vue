<template>
  <div id="nested" style="width: 100%; height: 300px">
    
  </div>
</template>

<script>
import echarts from 'echarts';
export default {
  name: 'nested',
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
        tooltip: {
          trigger: 'item',
          formatter: "{a} <br/>{b}: {c} ({d}%)"
        },
        legend: {
          x: 'center',
          data:['直达','营销广告','搜索引擎','邮件营销']
        },
        series: [
          {
            name:'访问来源',
            type:'pie',
            selectedMode: 'single',
            radius: [0, '30%'],
            label: {
              normal: {
                  position: 'inner'
              }
            },
            labelLine: {
              normal: {
                  show: false
              }
            },
            data:[
              {value:335, name:'直达', selected:true},
              {value:679, name:'营销广告'},
              {value:1548, name:'搜索引擎'}
            ]
          },
          {
              name:'访问来源',
              type:'pie',
              radius: ['40%', '55%'],
              label: {
                  normal: {
                      formatter: '{per|{c}件}\n{b|{b}}',
                      rich: {
                          b: {
                            fontSize: 16,
                            lineHeight: 33
                          },
                          per: {
                            fontSize: 20,
                            padding: [2, 4],
                          }
                      }
                  }
              },
              data:[
                  {value:335, name:'直达'},
                  {value:310, name:'邮件营销'},
                  {value:234, name:'联盟广告'},
                  {value:135, name:'视频广告'},
              ]
          }
        ]
      }
    }
  },
  methods: {
    draw() {
      console.log(this)
      this.chart = echarts.init(document.getElementById('nested'))
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
