<template>
  <div class="animated fadeIn">
    <div style="padding-bottom: 30px">
      <div style="padding-bottom: 30px">
      <span class="underline">
        <div style="float:left;">
          <h1>{{header}}</h1>
        </div>
        <!--<div style="float:right; margin-right: 30px;">-->
          <!--<b-col class="text-center mt-2" style="padding-right: 0px; padding-left: 10px">-->
            <!--<b-button variant="secondary">-->
              <!--<i class="cui-speech"></i>-->
            <!--</b-button>-->
          <!--</b-col>-->
        <!--</div>-->
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
  </div>
</template>

<script>
  import SimpleLineIcons from "../icons/SimpleLineIcons.vue";
  import db from '/Users/user/WebstormProjects/CoreUI-Vue/src/views/pages/firebaseInit.js';


  export default {
    components: {SimpleLineIcons},
    name: 'progress',
    data(){
      return {
        header: null,
        copywriter:
          {
            name: null,
            email: null,
            image: null
          }
        ,
        curator:
          {
            name: null,
            email: null,
            image: null
          }
        ,
        progress:
          {
            pages_complete: null,
            pages_total: null,
            est_date: null,
            est_month: null
          }
      }
    },
    beforeRouteEnter (to, from, next) {
      db.collection('Users').get().then
      (querySnapshot => {
        querySnapshot.forEach(doc =>{
          if(doc.id == to.params.story_id) {
            next(vm => {
              vm.header = doc.data().Title,
              vm.copywriter.name = doc.data().copyname
              vm.copywriter.email = doc.data().copyemail
              vm.copywriter.image = doc.data().copyimg
              vm.curator.name = doc.data().curatorname
              vm.curator.email = doc.data().curatoremail
              vm.curator.image = doc.data().curatorimg
              vm.progress.pages_complete = doc.data().completedpages
              vm.progress.pages_total = doc.data().totalpages
              vm.progress.est_date = doc.data().estday
              vm.progress.est_month = doc.data().estmonth
            next();
          })
          }
        })
      })
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
