<template>
  <div class="animated fadeIn">
    <div style="padding-bottom: 30px">
      <div class="header"><h1>{{header}}</h1></div>
    </div>
    <div style="display: block; margin: 0 auto">
      <h1 style="text-align: center; padding-top: 40px; color: #585858">Coming Soon</h1>
      <p style="text-align: center; margin-bottom: 1px; color: #696969; padding-bottom: 50px" >
        Track usage across platforms and see which stories have the biggest reach.<br>Understand your audience through A/B Testing.
      </p>
      <img style="height: 60px; display:block; margin: 0 auto" src="http://gifimage.net/wp-content/uploads/2017/08/loading-gif-transparent-10.gif"/>
    </div>
  </div>
</template>

<script>
  import MainChartExample from '@/views/dashboard/MainChartExample'

  export default {
    name: 'analytics',
    components:{
      MainChartExample,
    },
    data(){
      return {
        header: 'Analytics'
      }
    }
  }
</script>

<style scoped>
  .header{
    border-bottom: solid;
    border-width: 1px;
    border-color: darkgray;
    padding-top: 30px;
  }
</style>
