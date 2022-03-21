<template>
  <div class="kakaoStory">
    <div class="tagMenu">
      <div class="tag">
        <input type="radio" name="tag" id="cafe" checked @click="radioClick($event)" value="0">
        <input type="radio" name="tag" id="branch" @click="radioClick($event)" value="1">
        <input type="radio" name="tag" id="tstory" @click="radioClick($event)" value="2">
        <input type="radio" name="tag" id="kastory" @click="radioClick($event)" value="3">

        <div class="cafe"><label for="cafe" :style="[tag[0].boo?offBlue:onBlue]">{{tag[0].value}}</label></div>
        <div class="branch"><label for="branch" :style="[tag[1].boo?offBlue:onBlue]">{{tag[1].value}}</label></div>
        <div class="tstory"><label for="tstory" :style="[tag[2].boo?offBlue:onBlue]">{{tag[2].value}}</label></div>
        <div class="kastory"><label for="kastory" :style="[tag[3].boo?offBlue:onBlue]">{{tag[3].value}}</label></div>
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
    <div class="tagContents"><StotyOne/></div>
  </div>
</template>

<script>
import StotyOne from '@/components/StoryOne.vue'
export default {
  components:{
    StotyOne,
  },
  mounted(){
    var radioId = window.$("input[name='tag']:checked").val();
    this.tag[radioId].boo = false;
    this.count=parseInt(radioId)+1;
  },
  data(){
    return{
      count:1,
      tagChange:[true,false,false,false],
      onBlue: {'color': '#01C1FA', 'text-decoration': 'underline',},
      offBlue: {'color': 'black', 'text-decoration': 'none'},
      tag:[
        {id:"cafe", value:"카페",boo:"true"},
        {id:"branch", value:"브런치",boo:"false"},
        {id:"tstory", value:"티스토리",boo:"false"},
        {id:"kastory", value:"카카오스토리",boo:"false"},
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
.kakaoStory{
  border-top: 1px solid black;
  width: 100%;
  height: 100%;
}
.kakaoStory .tagMenu{
  width: 100%;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.kakaoStory .tagMenu .tag{
  width: 200px;
  height: 100%;
  margin-left: 1px;
  margin-right: 1px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Cute Font', cursive;
}
.kakaoStory .tagMenu .tag input{display: none;}
.kakaoStory .tagMenu .tag .cafe, .kakaoStory .tagMenu .tag .branch, .kakaoStory .tagMenu .tag .tstory, .kakaoStory .tagMenu .tag .kastory{
  font-size: 20px;
}
.kakaoStory .tagMenu .tag label:hover{cursor: pointer;}
.kakaoStory .tagMenu .tagradio div{display: inline-block;}

.kakaoStory .tagMenu .tagradio .counting{margin-right: 10px;}
.kakaoStory .tagMenu .tagradio .buttons button{background: white; border: 1px solid rgba(128,128,128,0.5);}

.kakaoStory .tagContents{
  width: 100%;
  height: calc(550px - 50px - 60px);
  margin-top: 5px;
  margin-bottom: 5px;
}
</style>
