<template>
  <div class="hello">
    <h1>铃音列表</h1>
    <ul>
      <!-- <li v-for="(music,index) in list" :key="index" @dblclick="select" :data-src="music.src">
        {{music.title}}
         <av-bars
        :audio-src="music.src">
      </av-bars>
      </li> -->
      <li>
        <p>一条大河</p>
         <av-bars
         audio-src="./static/bach.mp3">
      </av-bars>
      </li>
        <li>
          <p>三万英尺</p>
           <av-line
          :line-width="2"
          line-color="lime"
          audio-src="./static/三万英尺.mp3"
    ></av-line>
        </li>
      <li>  
        <p>甜蜜蜜</p>
            <av-circle
              :outline-width="0"
              :progress-width="5"
              :outline-meter-space="5"
              :playtime="true"
              playtime-font="18px Monaco"
              audio-src="/static/甜蜜蜜.mp3"
    ></av-circle>
      </li>
    </ul>
    
     
  </div>

      
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      list:[
        {
          title:"一条大河",
          src:"/static/bach.mp3"
        },
        {
          "title":"三万英尺~迪克牛仔",
          src:"/static/bach.mp3"
        }
      ],
      selected:"/static/bach.mp3"
    }
  },
  methods:{
    select(e){
      console.log(e.target.getAttribute("data-src"));
      this.selected=e.target.getAttribute("data-src");
    }
  },
  watch:{
    selected(){
      console.log("changed")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul>li{
  list-style:none;
}
.hello{
  width:80%;
  margin:0 auto;
  border:1px solid #ddd;
  box-shadow: 0 0 2px 2px #ddd;
  padding:5%;
}
</style>
