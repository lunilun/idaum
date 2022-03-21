<template>
  <div class="today">

     <div class="previmg">
      <img :src="prev" alt="" width="180px" height="510px" v-show="isViewPre"><div class="noImg" v-show="!isViewPre"><button @click="moreImgPage">더 많은 이미지 보러가기</button></div>
    </div>
    <div class="nowimg">
      <vueper-slides
        ref="vueperslides1"
        :touchable="false"
        fade
        :autoplay="false"
        :bullets="false"
        :arrows="false"
        :arrows-outside="true"
        @slide="$refs.vueperslides2.goToSlide($event.currentSlide.index, { emit: false })"
        fixed-height="290px">
        <vueper-slide v-for="(slide, i) in slides" :key="i" :image="slide.image">
          <template #content>
            <div class="innertxt" @click="goImgPage(i)">{{contentsinner[i].content}}</div>
          </template>
        </vueper-slide>
      </vueper-slides>

      <vueper-slides
        class="no-shadow thumbnails"
        ref="vueperslides2"
        :arrows-outside="false"
        :visible-slides="6"
        slide-multiple
        :slide-ratio="1 / 7"
        :bullets="false"
        :dragging-distance="200"
        :breakpoints="{ 800: { visibleSlides: 3, slideMultiple: 2 } }"
        :gap="1"
        :arrows="true">
        <vueper-slide
          v-for="(slide, i) in slides"
          :key="i"
          :image="slide.image"
          @click.native="$refs.vueperslides1.goToSlide(i), prennexting(i)">
        </vueper-slide>
      </vueper-slides>
    </div>

    <div class="nextimg">
      <img :src="next" alt="" width="500px" height="510px" v-show="isViewNext"><div class="noImg" v-show="!isViewNext"><button @click="moreImgPage">더 많은 이미지 보러가기</button></div>
    </div>

  </div>
</template>

<script>
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

export default ({
  components:{
    VueperSlides, 
    VueperSlide
  },
  created(){
    this.next=this.slides[this.count+1].image;
  },
  data(){
    return{
      count:0,
      prev:'',
      next:'',
      isViewPre:false,
      isViewNext:true,
      slides:[
        {id:1, image: require('../Image/Today/back1.png') },
        {id:2, image: require('../Image/Today/back2.png') },
        {id:3, image: require('../Image/Today/back3.png') },
        {id:4, image: require('../Image/Today/back4.png') },
        {id:5, image: require('../Image/Today/back5.png') },
        {id:6, image: require('../Image/Today/back6.png') },
        {id:7, image: require('../Image/Today/back7.png') },
        {id:8, image: require('../Image/Today/back1.png') },
        {id:9, image: require('../Image/Today/back2.png') },
        {id:10, image: require('../Image/Today/back3.png') },
        {id:11, image: require('../Image/Today/back4.png') },
        {id:12, image: require('../Image/Today/back5.png') },
        {id:13, image: require('../Image/Today/back6.png') },
        {id:14, image: require('../Image/Today/back7.png') },
        {id:15, image: require('../Image/Today/back1.png') },
        {id:16, image: require('../Image/Today/back2.png') },
        {id:17, image: require('../Image/Today/back3.png') },
        {id:18, image: require('../Image/Today/back4.png') },
        {id:19, image: require('../Image/Today/back5.png') },
        {id:20, image: require('../Image/Today/back6.png') },
        {id:21, image: require('../Image/Today/back7.png') },
      ],
      contentsinner:[
        { content: "1<This is image page number>" },
        { content: "2<This is image page number>" },
        { content: "3<This is image page number>" },
        { content: "4<This is image page number>" },
        { content: "5<This is image page number>" },
        { content: "6<This is image page number>" },
        { content: "7<This is image page number>" },
        { content: "8<This is image page number>" },
        { content: "9<This is image page number>" },
        { content: "10<This is image page number>" },
        { content: "11<This is image page number>" },
        { content: "12<This is image page number>" },
        { content: "13<This is image page number>" },
        { content: "14<This is image page number>" },
        { content: "15<This is image page number>" },
        { content: "16<This is image page number>" },
        { content: "17<This is image page number>" },
        { content: "18<This is image page number>" },
        { content: "19<This is image page number>" },
        { content: "20<This is image page number>" },
        { content: "21<This is image page number>" },
      ]
    }
  },
  methods: {
    goImgPage(i){
      alert((i+1)+"번 이미지 페이지로 이동합니다.");
    },
    moreImgPage(){
      alert("모든 이미지 페이지로 이동합니다.");
    },
    prennexting(i){
      var nnext=i+1;
      var npre=i-1;
      if(i!=0) {
        this.prev = this.slides[npre].image;
        this.isViewPre = true;
      }
      else this.isViewPre=false;

      if(i!=this.slides.length-1) {
        this.next = this.slides[nnext].image;
        this.isViewNext = true;
      }
      else this.isViewNext=false;
      
    }
  },
})
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Cute+Font&display=swap');
/* font-family: 'Cute Font', cursive; */
.today{
  width: 1050px;
  height: 400px;
  display: flex;
  justify-content: space-between;
}
.today .nowimg{
  width: 800px;
  height: 400px;
}
.thumbnails{
  margin-top: 10px;
}
.innertxt{
  width: 800px;
  height: 100%;
  background: rgba(128,128,128,.4);
  position: absolute;
  font-size: 30px;
  z-index: 10;
  color: white;
  top: 70%;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
  font-family: 'Cute Font', cursive;
}
.innertxt:hover{cursor: pointer;}
.previmg{
  width: 200px;
  height: 400px;
  margin-right: 4px;
  overflow: hidden;
}
.nextimg{
  width: 200px;
  height: 400px;
  margin-left: 4px;
  overflow: hidden;
}
.previmg, .nextimg{opacity: .7;}
.noImg{
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.noImg button{
  width: 150px;
  height: 50px;
  background: white;
  border-radius: 20px;
  font-size: 15px;
  font-family: 'Cute Font', cursive;
}
.noImg button:hover{
  cursor: pointer;
  transform: translateY(-10px);
  transition: all .3s;
}
</style>
