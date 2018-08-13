<template>
  <div class="animated fadeIn">
    <div style="padding-bottom: 5px">
      <span class="underline">
        <div style="float:left;">
          <h1>{{header}}</h1>
        </div>
      </span>
    </div>
    <div>
        <iframe :src= "url" height="580px" width="100%"> </iframe>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'chat',
    data(){
      return {
        header: 'New Story',
        url: 'https://lex-web-ui-codebuilddeploy-1hla9mip1-webappbucket-1t4tuzbtxhbyi.s3.amazonaws.com/index.html'
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
