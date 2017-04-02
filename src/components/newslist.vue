<template> 
  <div class="newslist">
    <section class="hero  is-warning is-bold">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            {{source.name}}<span v-if="!source">We will</span> give the all updates that u need to know about..
          </h1>
          <h2 class="subtitle">
            {{source.category}}
          </h2>
        </div>
        <a v-if="source" :href="source.url" target="_blank" class="newsButton button is-danger">Visit Us..</a>
      </div>
    </section>
    <div class="container">
      <div  class="lists">
        <div  class="columns">
          <div v-for="article in articles" class="column is-4">
            <div  class="card">
              <div class="card-image">
                <figure class="image is-4by3">
                <img :src="article.urlToImage" alt="Image">
                </figure>
              </div>
              <div class="card-content">
                  <div class="media">
                    <div class="media-left">
                      <figure class="image is-48x48">
                      <img :src="source.urlsToLogos.large" alt="Image">
                      </figure>
                    </div>
                    <div class="media-content">
                      <p class="title is-4">{{article.author}}</p>
                      <p class="subtitle is-6">@{{article.author}}</p>
                    </div>
                  </div>

                <div class="content">
                  {{article.title}}<a>@{{article.author}}</a>.
                  <a></a> <a>#{{source.category}}</a>
                  <br>
                  <small>{{article.publishedAt}}</small>
                </div>
                <nav class="level is-mobile">
                  <div class="level-left">
                    <a class="level-item">
                      <span class="icon is-small"><i class="fa fa-reply"></i></span>
                    </a>
                    <a class="level-item">
                      <span class="icon is-small"><i class="fa fa-retweet"></i></span>
                    </a>
                    <a class="level-item">
                      <span class="icon is-small"><i class="fa fa-heart"></i></span>
                    </a>
                  </div>
                </nav>
                  <a :href="article.url" class="button is-primary is-outlined" target="_blank">Read more..</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  export default {

    name:'newslist',
    props:['source'],

    data(){
      return{
        articles:[]
      }
    },
    methods:{
        updateSource(source){
          if(source){
            this.$http.get('https://newsapi.org/v1/articles?source='+ source.id +'&apiKey=8f1d31cb271f4c939e6e7550b46bc4e3').then(response =>{
              this.articles = response.data.articles;
            });
          }
        }
    },
    created(){
      this.updateSource(this.source); 
    },
    watch:{
      source(value){
        this.updateSource(value);
      }
    }
  }
</script>
<style scoped>

.first{
  overflow: hidden;
  width: 100%;
  height: 100%;
  background-size: 100% 100%;
  background-repeat: no-repeat;
}
.first:hover > .overlay{
   transition: 0.5s ease-in-out;
  opacity: 0.8; 
   position: relative;
   bottom: -48%;
}
.overlay{
  /*margin-top: 60%;*/
  transition: 0.5s ease-in-out;
    position: relative;
    bottom:-150%;
    opacity: 0;
}
.columns{
  flex-wrap: wrap;
}
.card{
  overflow: hidden;
  box-shadow: 2px 4px 10px 3px rgba(0,0,0,0.2);
}
.level{
  float: right;
}
.hero{
  margin-bottom: 20px;
  color: #fff;
}
.newsButton{
  position: relative;
  left:70%;
  animation: slide 5s 2s 3 ease-in-out;
}
@keyframes slide{
  from{
    left:10%;
  }
  to{
    left:70%;
  }
}
</style>