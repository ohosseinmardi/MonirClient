<template>
  <div class="animated fadeIn">
    <div style="padding-bottom: 30px">
      <div class="header">
        <h1>{{header}}</h1>
      </div>
    </div>
    <b-row>
      <b-card border-variant="warning" class = "shadow" style="width: 250px; margin: 5px;">
        <div slot="footer">
          <p class="title">{{story1.title}}</p>
          <p class="date">{{story1.date}}</p>
          <b-badge variant="warning" class="float-right">{{story1.info}}</b-badge>
        </div>
        <a href="#/base/progress">
          <img class = "img" :src= "story1.img" alt="">
          <div class="info">
          </div>
        </a>
      </b-card>
      <b-card border-variant="success" class = "shadow" style="width: 250px; margin: 5px;">
        <div slot="footer">
          <p class="title">{{story2.title}}</p>
          <p class="date">{{story2.date}}</p>
        </div>
        <a href="#/base/finishedstory">
          <img class = "img" :src= "story2.img" alt="">
          <div class="info">
          </div>
        </a>
      </b-card>
      <b-card border-variant="success" class = "shadow" style="width: 250px; margin: 5px;">
        <div slot="footer">
          <p class="title">{{story3.title}}</p>
          <p class="date">{{story3.date}}</p>
          <b-badge variant="warning" class="float-right">{{story3.info}}</b-badge>
        </div>
          <img class = "img" :src= "story3.img" alt="">
          <div class="info">
          </div>
      </b-card>
    </b-row>
  </div>
</template>

<script>
  export default {
    name: 'stories',
    data(){
      return{
        story1: {
          img: 'http://story.monir.media/images/fannyiphone.png',
          title: 'Fanny IPA',
          date: 'In progress',
          info: 'Collecting Assets'
        },
        story2: {
          img: 'http://story.monir.media/images/bowieiphone.png',
          title: 'David Bowie',
          date: 'May 18',
          info: ''
        },
        story3: {
          img: 'http://story.monir.media/images/gettyiphone.png',
          title: 'Getty FOTO',
          date: 'April 28',
        },
        header: 'All Stories'
      }
    }
  }
</script>


<style scoped>

  .shadow{
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1), 0 6px 20px 0 rgba(0, 0, 0, 0.05);

  }
  .header{
    border-bottom: solid;
    border-width: 1px;
    border-color: darkgray;
    padding-top: 30px;
  }
  .title {
    font-weight: 400;
    font-family: Avenir, Lato;
    font-size: 18px;
    text-align: left;
    margin: 0 auto;
    float: none;
  }
  .info{
    padding-right: 35px;
  }
  .date {
    font-weight: 300;
    font-family: Avenir, Lato;
    font-size: 12px;
    color: grey;
    text-align: left;
    margin: 0 auto;
    float: left;
  }
  .img {
    width: 100%;
    border: none;
    display: block;
    margin: 0 auto;
  }
  .fade-enter-active {
    transition: all .3s ease;
  }
  .fade-leave-active {
    transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }
  .fade-enter, .fade-leave-to {
    transform: translateX(10px);
    opacity: 0;
  }
</style>
