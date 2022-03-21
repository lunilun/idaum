<template>
  <div class="kakaotv">
    <div class="tagMenu">
      <div class="tag">
        <p>카카오TV</p>
        <input type="radio" name="tag" id="original" checked @click="radioClick($event)" value="0">
        <input type="radio" name="tag" id="highlight" @click="radioClick($event)" value="1">
        <input type="radio" name="tag" id="tvmain" @click="radioClick($event)" value="2">

        <div class="original"><label for="original" :style="[tag[0].boo?offBlue:onBlue]">{{tag[0].value}}</label></div>
        <div class="highlight"><label for="highlight" :style="[tag[1].boo?offBlue:onBlue]">{{tag[1].value}}</label></div>
        <div class="tvmain"><label for="tvmain" :style="[tag[2].boo?offBlue:onBlue]">{{tag[2].value}}</label></div>

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
    <div class="tagContents"><TvOne/></div>
  </div>
</template>

<script>
import TvOne from '@/components/TvOne.vue'
export default {
  components:{
    TvOne,
  },
  mounted(){
    var radioId = window.$("input[name='tag']:checked").val();
    this.tag[radioId].boo = false;
    this.count=parseInt(radioId)+1;
  },
  data(){
    return{
      count:1,
      tagChange:[true,false,false],
      onBlue: {'color': '#01C1FA', 'text-decoration': 'underline',},
      offBlue: {'color': 'gray', 'text-decoration': 'none'},
      tag:[
        {id:"original", value:"오리지날 콘텐츠",boo:"true"},
        {id:"highlight", value:"TV 하이라이트",boo:"false"},
        {id:"tvmain", value:"TV 주요장면",boo:"false"},
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
.kakaotv{
  border-top: 1px solid black;
  width: 100%;
  height: 100%;
}
.kakaotv .tagMenu{
  width: 100%;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.kakaotv .tagMenu .tag{
  width: 300px;
  height: 100%;
  margin-left: 1px;
  margin-right: 1px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Cute Font', cursive;
  font-size: 25px;
}
.kakaotv .tagMenu .tag input{display: none;}
.kakaotv .tagMenu .tag .original, .kakaotv .tagMenu .tag .highlight, .kakaotv .tagMenu .tag .tvmain{
  font-size: 18px;
}
.kakaotv .tagMenu .tag label:hover{cursor: pointer;}
.kakaotv .tagMenu .tagradio div{display: inline-block;}

.kakaotv .tagMenu .tagradio .counting{margin-right: 10px;}
.kakaotv .tagMenu .tagradio .buttons button{background: white; border: 1px solid rgba(128,128,128,0.5);}

.kakaotv .tagContents{
  width: 100%;
  height: calc(550px - 50px - 60px);
  margin-top: 5px;
  margin-bottom: 5px;
}
#snapper{font-size: 13px;}
</style>
