<template> 
  <div class="navbar">
    <div class="mainHeader">
        <nav class="nav">
          <div class="nav-left">
            <a class="nav-item">
              <h2 class="title is-2">NEX</h2>
            </a>
          </div>

          <div class="nav-center">
            <a class="nav-item">
              <span class="icon">
                <i class="fa fa-github"></i>
              </span>
            </a>
            <a class="nav-item">
              <span class="icon">
                <i class="fa fa-twitter"></i>
              </span>
            </a>
          </div>

          <!-- This "nav-toggle" hamburger menu is only visible on mobile -->
          <!-- You need JavaScript to toggle the "is-active" class on "nav-menu" -->
          <span class="nav-toggle">
            <span></span>
            <span></span>
            <span></span>
          </span>

          <!-- This "nav-menu" is hidden on mobile -->
          <!-- Add the modifier "is-active" to display it on mobile -->
          <div class="nav-right nav-menu">
            <a class="nav-item">
              Home
            </a>
            <a class="nav-item">
              About
            </a>
            <a class="nav-item">
              Blog
            </a>

            <span class="nav-item">
              <a class="button" >
                <span class="icon">
                  <i class="fa fa-twitter"></i>
                </span>
                <span>Tweet</span>
              </a>
              <a class="button is-primary">
                <span class="icon">
                  <i class="fa fa-ravelry"></i>
                </span>
                <span>Sources</span>
                <div class="field has-addons has-addons-centered">
                  <p class="control">
                    <span class="select">
                      <select  v-on:change="sourceChanged">
                        <option>Choose Source...</option>
                        <option :value="source.id" v-for="source in sources">{{source.name}}</option>
                      </select>
                    </span>
                  </p>
                </div>
              </a>
            </span>
          </div>
        </nav>
        <!-- news description -->
        <section class="hero is-primary is-bold">
          <div class="hero-body">
            <h2 v-if="!source" class="title is-2">{{message}}</h2>
            <div v-if="source" class="container">
              <div class="category" >
                <h4 class="title is-4">Category</h4><a class="button is-danger is-focused">{{source.category}}</a>   
              </div>
              <div>
                  <figure class="image image is-96x96">
                    <img :src="source.urlsToLogos.large">
                  </figure>
              </div>
              <h1 v-if="!source" class="title">
                {{source.name}}
              </h1>
              <h2 class="subtitle">
                {{source.description}}
              </h2>
            </div>
          </div>
        </section>
        <!-- end of news description -->
    </div>  
      <!-- main header -->
      <div v-if="source" class="container">
        <div class="heading">
          <h2 class="title is-2">{{title}}</h2>
          <h6 class="title is-6">Latest Updates</h6>
        </div>
        <div class="tile is-ancestor">
          <div class="tile is-parent">
            <div class="first" id="background" :style="{backgroundImage: 'url('+ articles[0].urlToImage +')'}">
              <div class="overlay">
                <article class="tile is-child box" >
                  <p class="title">{{title}}</p>
                  <div class="content">
                    <h3 class="is-3">{{articles[0].title}}</h3>
                  <a :href="articles[0].url" target="_blank" class="button is-focused">More..</a>
                  </div>
                </article>
              </div>
            </div>
          </div>
          <div class="tile is-parent is-6">
            <div class="first" id="background" :style="{backgroundImage: 'url('+ articles[1].urlToImage +')'}">
              <div class="overlay">
                <article  class="tile is-child box" >
                  <p class="title">{{title}}</p>
                  
                  <div class="content">
                    <h3 class="is-3">{{articles[1].title}}</h3>
                  <a :href="articles[1].url" target="_blank" class="button is-focused">More..</a>

                  </div>
                </article>
              </div>
            </div>
          </div>
          <div class="tile is-parent">
          <div class="first" id="background"  :style="{backgroundImage: 'url('+ articles[2].urlToImage +')'}">
            <div class="overlay">
              <article class="tile is-child box" >
                <p class="title">{{title}}</p>
                
                <div class="content">
                  <h3 class="is-3">{{articles[2].title}}</h3>
                  <a :href="articles[2].url" target="_blank" class="button is-focused">More..</a>

                </div>
              </article>
            </div>
          </div>
          </div>
      </div>
      <div class="tile is-ancestor">
        <div class="tile is-parent">
          <div class="first" id="background"  :style="{backgroundImage: 'url('+ articles[3].urlToImage +')'}">
            <div class="overlay">
              <article  class="tile is-child box">
                <p class="title">{{title}}</p> 
                <div class="content">
                  <h3 class="is-3">{{articles[3].title}}</h3>
                  <a :href="articles[3].url" target="_blank" class="button is-focused">More..</a>

                </div>
              </article>
            </div>
          </div>
        </div>
        <div class="tile is-parent is-8">
          <div class="first" id="background"  :style="{backgroundImage: 'url('+ articles[4].urlToImage +')'}">
            <div class="overlay">
              <article class="tile is-child box" >
                  <p class="title">{{title}}</p>
                  
                  <div class="content">
                    <h3 class="is-3">{{articles[4].title}}</h3>
                  <a :href="articles[4].url" target="_blank" class="button is-focused">More..</a>

                  </div>
              </article>
            </div>
          </div>
        </div>
      </div>

      <div class="tile is-ancestor">
        <div class="tile is-parent ">
        <div class="first" id="background"  :style="{backgroundImage: 'url('+ articles[5].urlToImage +')'}">
            <div class="overlay">
             <article  class="tile is-child box">
                <p class="title">{{title}}</p>
                <div class="content">
                  <h3 class="is-3">{{articles[5].title}}</h3>
                  <a :href="articles[5].url" target="_blank" class="button is-focused">More..</a>

                </div>
              </article>
            </div>
          </div>
        </div>
        <div class=" tile is-parent">
          <div class="first" id="background"  :style="{backgroundImage: 'url('+ articles[6].urlToImage +')'}">
              <div class="overlay">
              <article class="tile is-child box">
                <p class="title">{{title}}</p>
                <div class="content">
                  <h3 class="is-3">{{articles[6].title}}</h3>
                  <a :href="articles[6].url" target="_blank" class="button is-focused">More..</a>
                </div>
              </article>
            </div>
          </div>
        </div>  
      </div>
    </div>
    <!-- end of main header -->
  </div>
</template>

<script type="text/javascript">
  export default {
    name:'navbar',
    data() {
      return {
        sources:[],
        source:'',
        message:'Select the News Source which one you like.. ',
        title:'Tech',
        articles:[]
      }
    },
    methods:{
      sourceChanged(e){
        for(var i=0;i<=this.sources.length;i++){
          if(this.sources[i].id == e.target.value){
            this.source=this.sources[i];
          }
          this.$emit('sourceChanged',this.source);
        }   
      },
      fetchArticles(){
         this.$http.get('https://newsapi.org/v1/articles?source=the-verge&sortBy=latest&apiKey=8f1d31cb271f4c939e6e7550b46bc4e3').then(response =>{
            this.articles = response.data.articles;
          });
      }
    },
    created(){
      this.$http.get('https://newsapi.org/v1/sources?language=en').then(response =>{
        this.sources=response.data.sources;
      }),
         this.fetchArticles();
    }
  }
</script>
<style scoped>
.select{
  left: 10px;
  text-align: center;
}
.category{
  float: right;
  text-align: center;
}
.is-4{
  margin-bottom: 10px;
  cursor: default;
}
#background{
  background-size:100% 100%;
  background-repeat: no-repeat;

}
/*section .hero-body{

  background-color: #588C7E;
}
*/
a > span{
  cursor: default;
}
.container{
margin-top: 20px;
}

.first{
  overflow: hidden;
  box-shadow: 2px 4px 10px 3px rgba(0,0,0,0.2);
}
.first:hover > .overlay{
   transition: 0.5s ease-in-out; 
   position: relative;
   bottom:0%;
   opacity: 0.8;
}
.overlay{
    transition: 0.5s ease-in-out;
    position: relative;
    bottom:100%;
    opacity: 0;
}
.heading{
  font-family: 'Raleway', sans-serif;
}
.nav-item > h2{
  font-weight: bold;
}
</style>
 