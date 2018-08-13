<template>
  <div class="animated fadeIn">
    <div style="padding-bottom: 30px">
      <div class="header">
        <h1>{{header}}</h1>
      </div>
    </div>
    <b-row>
      <div v-for="item in stories">
        <b-card :border-variant="item.color" class = "shadow">
          <div slot="footer">
            <p class="title">{{item.title}}</p>
            <p class="date">{{item.date}}</p>
            <b-badge :variant="item.color" class="float-right">{{item.status}}</b-badge>
          </div>
          <router-link v-bind:to="{name: item.link ,params: {story_id: item.id}}">
            <img class = "img" :src= "item.img">
          </router-link>
        </b-card>
      </div>
    </b-row>
  </div>
</template>

<script>
  import db from '/Users/user/WebstormProjects/CoreUI-Vue/src/views/pages/firebaseInit.js';



  export default {
    name: 'testdb',
    data() {
      return {
        header: 'Test DB',
        stories: [],
        storyhtml: null
      }
    },
    created(){
      db.collection('Users').get().then
      (querySnapshot => {
        querySnapshot.forEach(doc =>{
          const data = {
            'id': doc.id,
            'title': doc.data().Title,
            'date': doc.data().date,
            'status': doc.data().status,
            'img': doc.data().img,
            'color': doc.data().color,
            'link': doc.data().link
          }
          this.stories.push(data)
        })
      })
      }
  }
</script>


<style>

  .shadow{
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1), 0 6px 20px 0 rgba(0, 0, 0, 0.05);
    width: 250px;
    margin: 5px;
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



