<template>
  <div class="animated fadeIn">
    <div style="padding-bottom: 30px">
      <div style="padding-bottom: 30px">
      <span class="underline">
        <div style="float:left;">
          <h1>{{header}}</h1>
        </div>
        <div style="float:right; margin-right: 30px;">
          <b-col class="text-center mt-2" style="padding-right: 0px; padding-left: 10px">
            <b-button variant="secondary">
              <i class="cui-speech"></i>
            </b-button>
          </b-col>
        </div>
      </span>
      </div>
    </div>
    <b-row>
      <div class= "box">
        <div class="inner-header"><h5>Latest Update</h5></div>
        <div class="infobox"><h5 style="padding-bottom: 20px">Pages Complete</h5><span style="display: inline"><h4 style="display: inline; color: #1e9ecb">{{progress.pages_complete}}</h4><p style="display: inline; color: gray"> out of </p><h4 style="display: inline;color: #1e9ecb">{{progress.pages_total}}</h4></span></div>
        <div class="infobox"><h5 style="padding-bottom: 20px">Estimated Completion Date</h5><span style="display: inline"><h4 style="display: inline; color: orangered;">{{progress.est_date}}</h4><p style="display: inline; color: gray"> {{progress.est_month}} </p></span></div>
      </div>
      <div class= "box2">
        <div style="width: 47%; float: left; margin: 5px">
          <div class="inner-header"><h5>Copywriter</h5></div>
        </div>
        <div style="width: 47%; float: right; margin: 5px"><div class="inner-header"><h5>Curator</h5></div></div>
        <div class="infobox" style="float: left; width: 47%; height: 75%;margin: 5px">
          <img class="img-class img-avatar" :src= "copywriter.image"/>
          <h5 style="float: left; margin-top: 50px; margin-left: 88px; margin-bottom: 0px">{{copywriter.name}}</h5>
          <p style="float: left; color: gray; margin-left: 89px;">{{copywriter.email}}</p>
        </div>
        <div class="infobox" style="float: right; width: 47%; height: 75%;margin: 5px">
          <img class="img-class img-avatar" :src= "curator.image"/>
          <h5 style="float: left; margin-top: 50px; margin-left: 88px; margin-bottom: 0px">{{curator.name}}</h5>
          <p style="float: left; color: gray; margin-left: 89px;">{{curator.email}}</p>
        </div>

      </div>
    </b-row>
    <h1 style="text-align: center; padding-top: 40px"> Your Story is being built</h1>
    <p style="text-align: center; margin-bottom: 1px" >
      We will notify you when its ready for review.
    </p>
    <p style="text-align: center;" >
      Feel free to come back to check on the status of your story.
    </p>
    <img style="height: 60px; display:block; margin: 0 auto" src="http://gifimage.net/wp-content/uploads/2017/08/loading-gif-transparent-10.gif"/>
  </div>
</template>

<script>
  import SimpleLineIcons from "../icons/SimpleLineIcons.vue";

  export default {
    components: {SimpleLineIcons},
    name: 'progress',
    data(){
      return {
        header: 'Fanny IPA',
        copywriter:
          {
            name: 'Samual Spencer',
            email: 'sasp@monir.media',
            image: 'img/avatars/8.jpg'
          }
        ,
        curator:
          {
            name: 'Abigail Enno',
            email: 'anhu@monir.media',
            image: 'img/avatars/5.jpg'
          }
        ,
        progress:
          {
            pages_complete: '4',
            pages_total: '10',
            est_date: '24',
            est_month: 'June'
          }
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
  .img-class{
    position: absolute;
    margin-top: 30px;
    width:80px;
    height:80px;
    float: left;
  }
  .infobox{
    border-bottom: solid;
    border-width: 1px;
    border-color: lightgray;
    background-color: white;
    border-style: solid;
    border-radius: 5px;
    width: 100%;
    height: 40%;
    display: block;
    margin-top: 15px;
    padding: 15px;
  }
  .box{
    border-bottom: solid;
    border-width: 1px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1), 0 6px 20px 0 rgba(0, 0, 0, 0.05);
    border-color: white;
    background-color: white;
    width: 300px;
    height: 300px;
    border-style: solid;
    border-radius: 5px;
    margin: 10px;
    padding: 15px;
  }
  .box2{
    border-bottom: solid;
    border-width: 1px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1), 0 6px 20px 0 rgba(0, 0, 0, 0.05);
    border-color: white;
    background-color: white;
    width: 600px;
    height: 300px;
    border-style: solid;
    border-radius: 5px;
    margin: 10px;
    padding: 15px;
  }
  .inner-header{
    border-bottom: solid;
    border-width: 1px;
    border-color: darkgray;
  }
</style>
