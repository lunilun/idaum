<template>
  <div class="tages">
    <!-- max height:550px -->
    <div class="tagMenu">
      <div class="tag">
        <input type="radio" name="tag" id="news" checked @click="radioClick($event)" value="0">
        <input type="radio" name="tag" id="dot1" @click="radioClick($event)" value="1">
        <input type="radio" name="tag" id="dot2" @click="radioClick($event)" value="2">
        <input type="radio" name="tag" id="dot3" @click="radioClick($event)" value="3">
        <input type="radio" name="tag" id="entertain" @click="radioClick($event)" value="4">
        <input type="radio" name="tag" id="sport" @click="radioClick($event)" value="5">
        <input type="radio" name="tag" id="movie" @click="radioClick($event)" value="6">
        <input type="radio" name="tag" id="car" @click="radioClick($event)" value="7">
        <input type="radio" name="tag" id="realestate" @click="radioClick($event)" value="8">
          <!-- 자동으로 넘어가는 기능도 추가해야됨 -->
        <div class="news"><label for="news" :style="[tag[0].boo?offBlue:onBlue]">{{tag[0].value}}</label></div>
        <div class="dot1"><label for="dot1" :style="[tag[1].boo?offBlue:onBlue]">{{tag[1].value}}</label></div>
        <div class="dot2"><label for="dot2" :style="[tag[2].boo?offBlue:onBlue]">{{tag[2].value}}</label></div>
        <div class="dot3"><label for="dot3" :style="[tag[3].boo?offBlue:onBlue]">{{tag[3].value}}</label></div>
        <div class="entertain"><label for="entertain" :style="[tag[4].boo?offBlue:onBlue]">{{tag[4].value}}</label></div>
        <div class="sport"><label for="sport" :style="[tag[5].boo?offBlue:onBlue]">{{tag[5].value}}</label></div>
        <div class="movie"><label for="movie" :style="[tag[6].boo?offBlue:onBlue]">{{tag[6].value}}</label></div>
        <div class="car"><label for="car" :style="[tag[7].boo?offBlue:onBlue]">{{tag[7].value}}</label></div>
        <div class="realestate"><label for="realestate" :style="[tag[8].boo?offBlue:onBlue]">{{tag[8].value}}</label></div>
      </div>
      <div class="tagradio">
        <div class="hiddenTxt" v-if="ishiddenMsg">
          <span id="issue">ISSUE</span><a href="">'코로나 19'현황</a>
        </div>
        <div class="counting">
          {{count}}/{{tag.length}}
        </div>
        <div class="buttons">
          <button @click="radioPre">◁</button>
          <button @click="radioNext">▷</button>
        </div>
      </div>
    </div>
    <div class="tagContents">
      <NewsOne/>
    </div>
    <div class="tagHome">
      <div class="viewtag">
        <!-- 이거 반복문으로 처리 가능할 듯 싶은데 -->
        <div class="tag_news" v-if="tagChange[0]">
          <a href="">뉴스홈<span>＞</span></a>
          <a href="">연재</a>
          <a href="">랭킹</a>
          <a href="">TV</a>
          <a href="">포토</a>
          <a href="">팩트체크</a>
        </div>

        <div class="tag_entertain" v-if="tagChange[4]">
          <a href="">연예홈<span>＞</span></a>
          <a href="">많이본뉴스</a>
          <a href="">TV영상</a>
          <a href="">포토</a>
          <a href="">투표</a>
          <a href="">스타봇</a>
        </div>

        <div class="tag_sport" v-if="tagChange[5]">
          <a href="">스포츠홈<span>＞</span></a>
          <a href="">축구</a>
          <a href="">해외축구</a>
          <a href="">야구</a>
          <a href="">해외야구</a>
          <a href="">골프</a>
          <a href="">농구</a>
          <a href="">배구</a>
          <a href="">일반</a>
          <a href="">e스포츠</a>
        </div>

        <div class="tag_movie" v-if="tagChange[6]">
          <a href="">영화홈<span>＞</span></a>
          <a href="">현재상영작</a>
          <a href="">상영예정작</a>
        </div>

        <div class="tag_car" v-if="tagChange[7]">
          <a href="">자동차홈<span>＞</span></a>
          <a href="">시승기</a>
          <a href="">COVER</a>
          <a href="">신차</a>
          <a href="">동영상</a>
        </div>

        <div class="tag_realestate" v-if="tagChange[8]">
          <a href="">부동산홈<span>＞</span></a>
          <a href="">주거</a>
          <a href="">분양</a>
          <a href="">인테리어</a>
          <a href="">뉴스</a>
          <a href="">커뮤니티</a>
        </div>

      </div>
      <div class="hiddenTag" v-if="ishiddenTag">
        <a href="">증시</a>
        <a href="">환율</a>
        <a href="">운세</a>
        <a href="">TV편성</a>
      </div>
    </div>
  </div>
</template>

<script>
import NewsOne from '@/components/NewsOne.vue'
export default {
  components:{
    NewsOne,
  },
  mounted(){
    var radioId = window.$("input[name='tag']:checked").val();
    this.tag[radioId].boo = false;
    this.count=parseInt(radioId)+1;
  },
  data(){
    return{
      count:1,
      ishiddenMsg:true,
      ishiddenTag:true,
      tagChange:[true,false,false,false,false,false,false,false,false],
      onBlue: {'color': '#01C1FA', 'text-decoration': 'underline',},
      offBlue: {'color': 'black', 'text-decoration': 'none'},
      tag:[
        {id:"news", value:"뉴스",boo:"false"},
        {id:"dot1", value:"●",boo:"false"},
        {id:"dot2", value:"●",boo:"false"},
        {id:"dot3", value:"●",boo:"false"},
        {id:"entertain", value:"연예",boo:"false"},
        {id:"sport", value:"스포츠",boo:"false"},
        {id:"movie", value:"영화",boo:"false"},
        {id:"car", value:"자동차",boo:"false"},
        {id:"realestate", value:"부동산",boo:"false"},
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

      if(selected==1 || selected==2 || selected==3) this.onBlue['text-decoration']='none';
      else this.onBlue['text-decoration']='underline'
      this.tag[selected].boo = false;
      this.count=parseInt(selected)+1;

      if(selected==0 || selected==1 || selected==2 || selected==3) {
        this.ishiddenMsg = true;
        this.ishiddenTag = true;
      }
      else{
        this.ishiddenMsg = false;
        this.ishiddenTag = false;
      }
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
      if(i==1 || i==2 || i==3 || i==4) this.onBlue['text-decoration']='none';
      else this.onBlue['text-decoration']='underline'

      if(i==1 || i==2 || i==3 || i==4) {
        this.ishiddenMsg = true;
        this.ishiddenTag = true;
      }
      else{
        this.ishiddenMsg = false;
        this.ishiddenTag = false;
      } 
    },
    changingTag(num,type){
      var count;
      if(type=="radio") count=num;
      else count=num-1; 

      for(var i=0;i<this.tag.length;i++){
        if(count==i){
          if(i==0||i==1||i==2||i==3) this.tagChange[0]=true;
          else this.tagChange[i]=true;
        }else{
          this.tagChange[i]= false;
         }
      }
    },
  },
};
</script>

<style scoped>
.tages{
  width: 100%;
  height: 100%;
}
.tages .tagMenu{
  width: 100%;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.tages .tagMenu .tag{
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
.tages .tagMenu .tag input{display: none;}
.tages .tagMenu .tag .dot1, .tages .tagMenu .tag .dot2, .tages .tagMenu .tag .dot3{
  margin-left: -8px;
  margin-right: -2px;
  font-size: 10px;
}
.tages .tagMenu .tag label:hover{cursor: pointer;}
.tages .tagMenu .tagradio div{display: inline-block;}
.tages .tagMenu .tagradio .hiddenTxt{margin-right: 10px; font-family: 'Cute Font', cursive;}
.tages .tagMenu .tagradio .hiddenTxt #issue{
  color: white;
  font-size: 20px;
  background: red;
  border: red;
  border-radius: 5px;
  padding: 2px;
}
.tages .tagMenu .tagradio .hiddenTxt #issue:hover{cursor: default;}
.tages .tagMenu .tagradio .hiddenTxt a{margin-left: 5px; font-size: 18px;}
.tages .tagMenu .tagradio .hiddenTxt a:hover{text-decoration: underline;color:#01C1FA;}
.tages .tagMenu .tagradio .counting{margin-right: 10px;}
.tages .tagMenu .tagradio .buttons button{background: white; border: 1px solid rgba(128,128,128,0.5);}

.tages .tagContents{
  width: 100%;
  height: 440px;
  margin-top: 5px;
  margin-bottom: 5px;
}
.tages .tagHome{
  width: 100%;
  height: 40px;
  background: rgba(128,128,128,.08);
  border: 1px solid rgba(128,128,128,0.3);
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Cute Font', cursive;
  font-size: 18px;
}
.tages .tagHome .viewtag a{
  margin-left: 10px;
  background: none;
  border: none;
  font-family: 'Cute Font', cursive;
  font-size: 18px;
}
.tages .tagHome .viewtag a:hover, .tages .tagHome .hiddenTag a:hover{text-decoration: underline; color:#01C1FA;}

.tages .tagHome .viewtag span{font-size: 12px; color: black;}
.tages .tagHome .hiddenTag a{margin-right: 10px;}

#snapper{font-size: 13px;}
</style>
