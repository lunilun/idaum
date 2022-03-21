<template>
  <div class="etc">
    <div class="tagMenu">
      <div class="tag">
        <input type="radio" name="tag" id="homecooking" checked @click="radioClick($event)" value="0">
        <input type="radio" name="tag" id="money" @click="radioClick($event)" value="1">
        <input type="radio" name="tag" id="animal" @click="radioClick($event)" value="2">
        <input type="radio" name="tag" id="style" @click="radioClick($event)" value="3">
        <input type="radio" name="tag" id="m" @click="radioClick($event)" value="4">
        <input type="radio" name="tag" id="travel" @click="radioClick($event)" value="5">
        <input type="radio" name="tag" id="work" @click="radioClick($event)" value="6">
        <input type="radio" name="tag" id="music" @click="radioClick($event)" value="7">
        <input type="radio" name="tag" id="webtoon" @click="radioClick($event)" value="8">
        <input type="radio" name="tag" id="game" @click="radioClick($event)" value="9">
        <input type="radio" name="tag" id="together" @click="radioClick($event)" value="10">

        <div class="homecooking"><label for="homecooking" :style="[tag[0].boo?offBlue:onBlue]">{{tag[0].value}}</label></div>
        <div class="money"><label for="money" :style="[tag[1].boo?offBlue:onBlue]">{{tag[1].value}}</label></div>
        <div class="animal"><label for="animal" :style="[tag[2].boo?offBlue:onBlue]">{{tag[2].value}}</label></div>
        <div class="style"><label for="style" :style="[tag[3].boo?offBlue:onBlue]">{{tag[3].value}}</label></div>
        <div class="m"><label for="m" :style="[tag[4].boo?offBlue:onBlue]">{{tag[4].value}}</label></div>
        <div class="travel"><label for="travel" :style="[tag[5].boo?offBlue:onBlue]">{{tag[5].value}}</label></div>
        <div class="work"><label for="work" :style="[tag[6].boo?offBlue:onBlue]">{{tag[6].value}}</label></div>
        <div class="music"><label for="music" :style="[tag[7].boo?offBlue:onBlue]">{{tag[7].value}}</label></div>
        <div class="webtoon"><label for="webtoon" :style="[tag[8].boo?offBlue:onBlue]">{{tag[8].value}}</label></div>
        <div class="game"><label for="game" :style="[tag[9].boo?offBlue:onBlue]">{{tag[9].value}}</label></div>
        <div class="together"><label for="together" :style="[tag[10].boo?offBlue:onBlue]">{{tag[10].value}}</label></div>

      </div>
      <div class="tagradio">
        <div class="counting">
          {{count}}/{{tag.length}}
        </div>
        <div class="buttons">
          <button @click="radioPre">◁</button>
          <button @click="radioNext">▷</button>
        </div>
      </div>
    </div>
    <div class="tagContents"><EtcOne/></div>
  </div>
</template>

<script>
import EtcOne from '@/components/EtcOne.vue'
export default {
  components:{
    EtcOne,
  },
  mounted(){
    var radioId = window.$("input[name='tag']:checked").val();
    this.tag[radioId].boo = false;
    this.count=parseInt(radioId)+1;
  },
  data(){
    return{
      count:1,
      tagChange:[true,false,false,false,false,false,false,false,false,false,false],
      onBlue: {'color': '#01C1FA', 'text-decoration': 'underline',},
      offBlue: {'color': 'black', 'text-decoration': 'none'},
      tag:[
        {id:"homecooking", value:"홈&쿠킹",boo:"true"},
        {id:"money", value:"머니",boo:"false"},
        {id:"animal", value:"동물",boo:"false"},
        {id:"style", value:"스타일",boo:"false"},
        {id:"m", value:"M+",boo:"true"},
        {id:"travel", value:"여행맛집",boo:"false"},
        {id:"work", value:"직장IN",boo:"false"},
        {id:"music", value:"뮤직",boo:"false"},
        {id:"game", value:"게임",boo:"true"},
        {id:"webtoon", value:"웹툰",boo:"false"},
        {id:"together", value:"같이가치",boo:"false"},
      ],
    }
  },
  methods:{
    resetRadio(){
      for(var i=0; i<this.tag.length;i++){
        this.tag[i].boo = true;
      }
    },
    radioClick(e){ 
      this.resetRadio();
      var selected = e.target.value;

      this.changingTag(selected,"radio");

      this.tag[selected].boo = false;
      this.count=parseInt(selected)+1;
    },
    radioPre(){
      this.resetRadio();
      this.count--;
      if(this.count<=0) this.count = this.tag.length;
      this.tag[this.count-1].boo = false; 

      this.buttonOnOff(this.count);
    },
    radioNext(){
      this.resetRadio();
      this.count++;
      if(this.count>this.tag.length) this.count = 1;
      this.tag[this.count-1].boo = false; 

      this.buttonOnOff(this.count);
    },
    buttonOnOff(i){
      this.changingTag(i,"button");
    },
    changingTag(num,type){
      var count;
      if(type=="radio") count=num;
      else count=num-1; 

      for(var i=0;i<this.tag.length;i++){
        if(count==i)
          this.tagChange[i]=true;
        else
          this.tagChange[i]= false;
      }
    },
  },
};
</script>

<style scoped>
.etc{
  border-top: 1px solid black;
  width: 100%;
  height: 100%;
}
.etc .tagMenu{
  width: 100%;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.etc .tagMenu .tag{
  width: 460px;
  height: 100%;
  margin-left: 1px;
  margin-right: 1px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Cute Font', cursive;
}
.etc .tagMenu .tag input{display: none;}
.etc .tagMenu .tag .cafe, .etc .tagMenu .tag .branch, .etc .tagMenu .tag .tstory, .etc .tagMenu .tag .kastory{
  font-size: 20px;
}
.etc .tagMenu .tag label:hover{cursor: pointer;}
.etc .tagMenu .tagradio div{display: inline-block;}

.etc .tagMenu .tagradio .counting{margin-right: 10px;}
.etc .tagMenu .tagradio .buttons button{background: white; border: 1px solid rgba(128,128,128,0.5);}

.etc .tagContents{
  width: 100%;
  height: calc(550px - 50px - 60px);
  margin-top: 5px;
  margin-bottom: 5px;
}
</style>
