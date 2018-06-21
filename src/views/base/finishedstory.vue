<template>
  <div class="animated fadeIn">
    <div style="padding-bottom: 30px">
      <span class="underline">
        <div style="float:left;">
          <h1>{{header}}</h1>
        </div>
        <div style="float:right; margin-right: 30px;">
          <b-col class="text-center mt-2" style="padding-right: 0px; padding-left: 10px">
            <b-button variant="secondary">
              Export
            </b-button>
          </b-col>
        </div>
        <div style="float:right;">
          <b-col class="text-center mt-2" style="padding-right: 0px; padding-left: 10px">
            <b-button variant="secondary">
              <i class="cui-speech"></i>
            </b-button>
          </b-col>
        </div>
        <div style="float:right;">
          <b-col class="mt-2" style="padding-right: 0px; padding-left: 10px">
            <b-button variant="secondary">
              <i class="cui-chart"></i>
            </b-button>
          </b-col>
        </div>
      </span>
    </div>
    <div>
      <iframe style="width: 100%; height: 590px" :src= "url"> </iframe>
      <iframe style=" height: 590px" :src= "url"> </iframe>

    </div>
  </div>
</template>

<script>
  export default {
    name: 'finishedstory',
    data(){
      return {
        header: 'David Bowie',
        url: 'http://story.monir.media/davidbowieis'
      }
    }
  }
</script>
<style>

  span.underline {
    border-bottom: solid;
    border-width: 1px;
    border-color: darkgray;
    display:inline-block;
    width: 100%;
    padding-top: 30px;
  }
  img.embeddedImage {
    vertical-align: middle;
  }

  #header {
    position: relative;
    width: 882px;
    z-index: 10;
    display: block;
    margin-left: auto;
    margin-right: auto;
    text-align: left;
    left: 44px;
  }

  #line-4 {
    position: relative;
    width: 825.8px;
    height: 6.375px;
    z-index: 10;
    display: block;
    margin-left: 25px;
    top: 1px;
    margin-top: -6px;
  }

  #david-bowie {
    position: relative;
    width: 137px;
    z-index: 20;
    text-align: left;
    color: rgb(0, 0, 0);
    font-weight: 500;
    font-family: Avenir, Lato;
    font-size: 24px;
    display: inline-block;
    height: 28px;
    margin-left: 4px;
  }

  #export {
    position: relative;
    width: 69px;
    z-index: 30;
    background-color: rgb(185, 184, 184);
    border-radius: 13px;
    display: inline-block;
    text-align: center;
    padding-top: 7px;
    margin-top: 5px;
    margin-left: 4px;
    padding-bottom: 7px;
  }

  #export-2 {
    position: relative;
    width: 39px;
    z-index: 10;
    text-align: center;
    color: rgb(233, 232, 232);
    font-weight: 500;
    font-family: Avenir, Lato;
    font-size: 10px;
    margin-right: auto;
    margin-left: auto;
    display: block;
    height: 12px;
  }

  #chat-history {
    position: relative;
    width: 35px;
    height: 27.7969px;
    z-index: 40;
    display: inline-block;
    margin-left: 1px;
    top: -1px;
  }

  #analytics {
    position: relative;
    width: 28.8px;
    height: 28.7969px;
    z-index: 50;
    display: inline-block;
    margin-top: 4px;
    margin-left: 593px;
  }

  section {
    width: 100%;
    left: 0px;
    position: relative;
    overflow: visible;
  }

  #img-2-section {
    z-index: 80;
    position: relative;
    display: inline-block;
    text-align: center;
    padding-top: 17px;
    padding-bottom: 13px;
  }
</style>
