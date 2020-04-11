<template>
   <div>
     <ul class="gallery">
       <li v-for="(n,index) in item" :key=index>
         <img
          @click="hightlight"
          :src=n
        >
         <div id="frame">
         <img :src="theatrical">
         </div>
       </li>
     </ul>
   </div>
</template>

<script>
export default {
  name: 'MyGallery',
  data(){
    return {
    theatrical: "",
    item:["http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg",
          "http://img1.qunarzz.com/piao/fusion/1802/42/7c92b9a381e46402.jpg_640x200_1cdce2a4.jpg",
          "http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg",
           "http://img1.qunarzz.com/piao/fusion/1801/1a/94428c6dea109402.jpg_640x200_2cf590d8.jpg"
         ]
  }
  },
  methods: {
     //点击图片放大展示
     hightlight(){
        this.theatrical=event.target.src;
        let eventIterator=event.target.parentNode;   //<li>
        while(eventIterator.previousElementSibling!=null){
          eventIterator.previousElementSibling.getElementsByTagName('img')[0].id="";
          eventIterator=eventIterator.previousElementSibling;
        }
        eventIterator=event.target.parentNode;
        while(eventIterator.nextElementSibling!=null){
          eventIterator.nextElementSibling.getElementsByTagName('img')[0].id=""
          eventIterator=eventIterator.nextElementSibling;
        }
     }
  },
 }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .gallery{
    display:flex;
    justify-content: space-around;
  }
  ul{
    list-style: none;
    padding:0;
  }
  li{
    display:inline-block;
    margin:0 10px;
  }
  img{
    width:20%
  }
  #theater{
    width:40%
  }
  #frame img {
  width: 80%;
}
</style>
