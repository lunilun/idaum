<template>
  <div class="home">

    <div class="header">
      <div class="mainlogo">
        <a href="" class="setstart">다음을 시작페이지로⮞</a>
        <img class="logo" src="../Image/img.jpg" alt="daum" width="180px" height="94px">
        <!-- <img src="../assets/logo.png" alt="daum" width="180px" height="94px"> -->
      </div>
      <div class="search">
        <div class="wrap">
          <input type="text" class="inputtxt">
          <span class="keyborad" @click="openKeyboard" :style="[isKeyboard?onclick:offclick]">🖮</span>
          <img class="MagniGlass" src="../Image/glass.png" alt="검색">
          <!-- <span class="MagniGlass">🔍</span> -->
          <div v-if="isKeyboard" class="virKeyboard">
            <div class="keys keyborad1">
              <span style="float:left">한글</span>
              <button style="float:right" @click="openKeyboard">X</button>
            </div>
            <div class="keys keyborads">
              <button class="">`</button>
              <button class="">1</button>
              <button class="">2</button>
              <button class="">3</button>
              <button class="">4</button>
              <button class="">5</button>
              <button class="">6</button>
              <button class="">7</button>
              <button class="">8</button>
              <button class="">9</button>
              <button class="">0</button>
              <button class="">-</button>
              <button class="">=</button>
              <button class="">←</button>
            </div>
            <div class="keys keyborads">
              <button class="">ㅂ</button>
              <button class="">ㅈ</button>
              <button class="">ㄷ</button>
              <button class="">ㄱ</button>
              <button class="">ㅅ</button>
              <button class="">ㅛ</button>
              <button class="">ㅕ</button>
              <button class="">ㅑ</button>
              <button class="">ㅐ</button>
              <button class="">ㅔ</button>
              <button class="">[</button>
              <button class="">]</button>
              <button class="">\</button>
            </div>
            <div class="keys keyborads">
              <button class="">ㅁ</button>
              <button class="">ㄴ</button>
              <button class="">ㅇ</button>
              <button class="">ㄹ</button>
              <button class="">ㅎ</button>
              <button class="">ㅗ</button>
              <button class="">ㅓ</button>
              <button class="">ㅏ</button>
              <button class="">ㅣ</button>
              <button class="">;</button>
              <button class="">'</button>
            </div>
            <div class="keys keyborads">
              <button class="">↑</button>
              <button class="">ㅋ</button>
              <button class="">ㅌ</button>
              <button class="">ㅊ</button>
              <button class="">ㅍ</button>
              <button class="">ㅠ</button>
              <button class="">ㅜ</button>
              <button class="">ㅜ</button>
              <button class="">ㅡ</button>
              <button class="">,</button>
              <button class="">.</button>
              <button class="">/</button>
              <button class="">-</button>
              <button class="">=</button>
              <button class="">↑</button>
            </div>
            <div class="keys keyborads">
              <button class="" style="width:85px">영문</button>
              <button class="" style="width:304px">간격</button>
              <button class="" style="width:85px">검색</button>
            </div>
          </div>
        </div>
        
        <div class="downcontents">
          <div class="downitem" v-for="(i,index) in visualList" v-bind:key="index">
            <div>{{i.content}}</div>
          </div>
          <button @click="next">▷</button>
          <button @click="prev">◁</button>
        </div>
      </div>
    </div>

    <div class="navi">
      <div class="wrap">
        <div class="left">
          <div class="inner">
            <div class="">카페</div>
            <div class="">메일</div>
            <div class="">뉴스</div>
            <div class="">지도</div>
            <div class="">증권</div>
            <div class="">쇼핑</div>
            <div class="">카카오TV</div>
            <div class="">웹툰</div>
            <div class="">캘린더</div>
            <div class="">브런치</div>
            <div class="">사전</div>
            <div class="">게임</div>
            <div class="">같이가치</div>
            <div class="more" @click="dropMenu" :style="checkDrop">
              <span>더보기</span>
              <span id="snapper" v-if="isdrop">{{dropTxt[1]}}</span>
              <span id="snapper" v-else-if="!isdrop">{{dropTxt[0]}}</span>
            </div>
          </div>
        </div>
        <div class="right">
          <div class="weather">
            <div>{{date}}</div>
            <div>부산시</div>
            <div>구름-2°C</div>
          </div>
        </div>
      </div>
    </div>

    <div class="mainarticle">
      <div class="wrap">
        <div class="left_article">
          <div class="advertise">
            <a href=""><img src="../Image/ad1.jpg" alt="광고이미지 NO.1" class="adimg1" width="100%" height="120px"></a> 
          </div>
          <div class="tages"><Tages/></div>
           <div class="kakaotv"><KakaoTV/></div>
          <div class="kakaostory"><KakaoStory/></div>
          <div class="etc"><Etc/></div>
        </div>
        <div class="right_article">
          <div class="login">
            <button class="kakaologin"><img class="kakaologo" src="../Image/kakao.png" alt="kakaologo">카카오계정으로 로그인</button>
            <button class="daumlogin"><img class="daumlogo" src="../Image/daum.png" alt="daumlogo">Daum아이디로 로그인</button>
            <div class="morelogin">
              <a href=""><img class="qr" src="../Image/qr.png" alt="qr">카카오 QR코드로 로그인</a>
              <a href=""><div>회원가입</div></a>
            </div>
          </div>
          <div class="advertise2">
            <div class="ad2Img"><img src="../Image/ad2.png" alt="광고이미지 NO.2" width="100%" height="150px"></div>
            <div class="ad2Txt">
              <div>삼성 다이렉트 공식 운전자<br>보험</div>
              <button>자세히 보기</button>
            </div>
          </div>
          <div class="shopping"><Shopping/></div>
          <div class="deal"><Hotdeal/></div>
          <div class="advertise3">
            <div class="ad2Img"><img src="../Image/ad2.png" alt="광고이미지 NO.2" width="100%" height="150px"></div>
            <div class="ad2Txt">
              <div>삼성 다이렉트 공식 운전자<br>보험</div>
              <button>자세히 보기</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="todayImg">
      <div class="wrap"><Today/></div>
    </div>

    <div class="footer">
      <div class="wrap">
        <div class="notice">
          <div class="noticemain">
            <img class="logo" src="../Image/img.jpg" alt="daum" width="52px" height="22px">
            <a href="" class="">공지사항</a><span id="snapper">＞</span><a href="">2022년 1월. Daum 모바일 뉴스가 달라집니다.</a>
          </div>
          <div class="noticeetc">
            <a href="">서비스전체보기</a><span id="snapper">＞</span>
          </div>
        </div>
        <div class="info">
          <div class="up">
            <a href="" class="">회사소개</a>
            <a href="" class="">비즈니스</a>
            <a href="" class="">맞춤형광고</a>
            <a href="" class="">검색등록</a>
            <a href="" class="">제휴문의</a>
            <a href="" class="">인재채용</a>
          </div>
          <div class="down">
            <a href="" class="">이용약관</a>
            <a href="" class="">통합정책</a>
            <a href="" class="">청소년보호정책</a>
            <a href="" class="">위치기반서비스이용약관</a>
            <a href="" class="">개인정보처리방침</a>
            <a href="" class="">웹접근성안내</a>
            <a href="" class="">고객센터</a>
          </div>
        </div>
        <div class="copyright">
          <span>Copyright @ Kakao Corp All right reserved</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Tages from '@/components/Tages.vue'
import KakaoTV from '@/components/KakaoTV.vue'
import KakaoStory from '@/components/KakaoStory.vue'
import Etc from '@/components/Etc.vue'
import Shopping from '@/components/Shopping.vue'
import Hotdeal from '@/components/Hotdeal.vue'
import Today from '@/components/Today.vue'

export default {
  name: "Home",
  created(){
    this.itemSet();
    for(var i=0; i<this.viewList.length/2;i++) this.visualList.push(this.viewList[i]);
    this.getToday();
  },
  components: {
    Tages,
    KakaoTV,
    KakaoStory,
    Etc,
    Shopping,
    Hotdeal,
    Today
  },
  data(){
    return{
      cnt:0,
      isKeyboard:false,
      onclick: {'font-weight': '600'},
      offclick: {'font-weight': '100'},
      itemList:[
        {no:0,content:'코로나19 발생현황'},{no:1,content:'전효성 하차소감'},{no:2,content:'컴퓨터 수리'},{no:3,content:'윈위 MV티저'},{no:4,content:'전원주택'},{no:5,content:'연말정산 간소화'},
        {no:6,content:'연기대상'},{no:7,content:'곰팡이 제거방법'},{no:8,content:'새해인사'},{no:9,content:'새해인사'},{no:10,content:'오징어 게임'},{no:11,content:'2022 휴일'},{no:12,content:'2022 임인년'}
      ],
      viewList:[],
      visualList:[],
      dropTxt:['⋁','⋀'],
      isdrop:false,
      checkDrop:{
        'color':'black',
      },
      date:'today',
    }
  },
  methods:{
    openKeyboard(){
      this.isKeyboard = !this.isKeyboard;
    },
    itemSet(){
      this.cnt=0;
      this.viewList.length=0;

      while(this.cnt<=7){
        var ran =  Math.floor(Math.random() * this.itemList.length);
        if(!this.viewList.includes(this.itemList[ran])) {
          this.viewList.push(this.itemList[ran]);
          this.cnt++;
        }
      }
    },
    next(){
      this.visualList.length=0;
      var start = this.viewList.length/2;
      var end = this. viewList.length;
      for(var i=start; i<end;i++) this.visualList.push(this.viewList[i]);
    },
    prev(){
      this.visualList.length=0;
      for(var i=0; i<this.viewList.length/2;i++) this.visualList.push(this.viewList[i]);
    },
    dropMenu(){
      this.isdrop = !this.isdrop;
      if(this.isdrop) this.checkDrop['color']= 'blue';
      else this.checkDrop['color']= 'black';
    },
    getToday(){
      var today = new Date();
      var week = new Array('일', '월', '화', '수', '목', '금', '토');
      var m = ('0' + (today.getMonth() + 1)).slice(-2);
      var d = ('0' + today.getDate()).slice(-2);
      this.date = m+"."+d+".("+week[today.getDay()]+")"
    }
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cute+Font&display=swap');
button:hover{cursor: pointer;}
ul{list-style: none;}
a{text-decoration: none; color: black;}
.logo:hover{cursor: pointer;}
.home{
  min-width: 1150px;
  position: relative;
}
/* 헤더 */
.header{
  position: relative;
  width: 1100px;
  height: 150px;
  margin: 0 auto;
}
.header .mainlogo{
  float: left;
  width: 180px;
  height: 150px;
}
.header .mainlogo .setstart{
  position: absolute;
  font-size: 12px;
  color: rgb(128, 128, 128,0.8);
}
.header .mainlogo .setstart:hover{
  color: skyblue;
  text-decoration: underline;
}
.header .mainlogo img{margin-top: 30px;}
.header .search{
  margin-top: 50px;
  float: left;
}
.header .search .wrap{
  position: relative;
  display: flex;
  align-items: center;
  height: 45px;
  margin-left: 5px;
  border: 1px solid rgb(0, 102, 255);
  border-radius: 1px;
}
.header .search .wrap:hover{
  border-image: linear-gradient(to right, red 0%, orange 100%);
  border-image-slice: 1;
}
.header .search .wrap .inputtxt{
  width: 380px;
  height: 40px;
  border: none;
  font-size: 12px;
}
.header .search .wrap .inputtxt:focus{
  outline: none;
  text-indent:10px;
}
.header .search .wrap .keyborad{
  color: blue;
  font-size: 25px;
  transform: translateY(-10%);
  margin-left: 5px;
  margin-right: 10px;
}
.header .search .wrap .MagniGlass{
  color: blue;
  font-size: 25px;
  margin-right: 5px;
}
.header .search .wrap .keyborad:hover, .header .search .wrap .MagniGlass:hover{cursor: pointer;}
.header .search .wrap .virKeyboard{
  position: absolute;
  z-index: 50;
  top: 50px;
  left: 300px;
  border: 1px solid black;
  padding: 15px;
  font-family: 'Cute Font', cursive;
  background: white;
  z-index: 100;
}
.header .search .wrap .virKeyboard .keys{height: 30px;}
.header .search .wrap .virKeyboard .keyborad1{font-size: 20px;}
.header .search .wrap .virKeyboard .keyborad1 button{
  background: none;
  border: none;
  color: gray;
  font-size: 20px;
}
.header .search .wrap .virKeyboard .keyborad1 button:hover{cursor: pointer;}
.header .search .wrap .virKeyboard .keyborads{
  display: flex;
  justify-content: center;
}
.header .search .wrap .virKeyboard .keyborads button{
  width: 30px;
  height: 30px;
  margin-left: 1px;
  margin-right: 1px;
  background: rgb(128, 128, 128,0.1);
  border: 1px solid black;
}
.header .search .downcontents{
  width: 450px;
  margin-top: 5px;
  margin-left: 5px;
  font-size: 20px;
  font-family: 'Cute Font', cursive;
}
.header .search .downcontents .downitem{
  display: inline-block;
  margin-right: 10px;
  color: gray;
}
.header .search .downcontents .downitem:hover{
  cursor: pointer;
  text-decoration: underline;
}
.header .search .downcontents button{
  float: right;
  background: white;
  width: 25px;
  height: 25px;
  margin-left: 1px;
  margin-right: 2px;
  border: 1px solid gray;
}
/* ------ */
/* 네비 */
.navi{
  margin-top: 4px;
  width: 100%;
  height: 50px;
  border-top: 1px solid rgba(0,0,0,0.1);
  border-bottom: 1px solid rgba(0,0,0);
}
.navi .wrap{
  width: 1100px;
  margin: 0 auto;
}
.navi .wrap .left{
  height: 50px;
  float: left;
}
.navi .wrap .left .inner{
  width: 650px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Cute Font', cursive;
  font-size: 21px;
}
#snapper{font-size: 13px;}
.navi .wrap .left .inner:hover{
  cursor: pointer;
}
.navi .wrap .right{
  height: 50px;
  float: right;
}
.navi .wrap .right .weather{
  width: 190px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Cute Font', cursive;
  font-size: 21px;
}
/* ------ */
/* 본문 */
.mainarticle{
  width: 100%;
  margin: 20px 0px;
  display: flex;
  flex-direction: column;
}
.mainarticle .wrap{
  width: 1050px;
  margin: 0 auto;
}
.mainarticle .wrap .left_article{
  float: left;
  width: 700px;
}
.mainarticle .wrap .left_article .advertise{
  width: 100%;
  height: 140px;
  border: 1px solid rgba(0,0,0,0.1);
}
/* 뭔가 애매함 */
.advertise2:hover{cursor: pointer;}
.advertise3:hover{cursor: pointer;}
/* ---------- */
.mainarticle .wrap .left_article .tages{
  width: 100%;
  height: 550px;
  margin-top: 10px;
}
.mainarticle .wrap .left_article .kakaotv{
  width: 100%;
  height: 200px;
  margin-top: 30px;
}
.mainarticle .wrap .left_article .kakaostory{
  width: 100%;
  height: 200px;
}
.mainarticle .wrap .left_article .etc{
  width: 100%;
  height: 540px;
  margin-top: 10px;
}
/* right */
.mainarticle .wrap .right_article{
  float: right;
  width: calc(100% - 750px);
  height: 100%;
}
.mainarticle .wrap .right_article .login{
  width: 100%;
  height: 140px;
  border: 1px solid rgba(0,0,0,0.1);
  background: rgba(128,128,128,0.1);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: 'Cute Font', cursive;
}
.mainarticle .wrap .right_article .login button{
  width: 80%;
  height: 40px;
  margin: 5px 0px 5px 0px;
  font-family: 'Cute Font', cursive;
  font-size: 23px;
}
.mainarticle .wrap .right_article .login button:nth-child(1){
  background: yellow;
  border: 1px solid rgba(0,0,0,.1);
}
.mainarticle .wrap .right_article .login .kakaologin .kakaologo{
  display: inline-block;
  margin-right: 4px;
  transform: translateY(20%);
}
.mainarticle .wrap .right_article .login button:nth-child(2){
  background: white;
  border: 1px solid rgba(0,0,0,.1);
}
.mainarticle .wrap .right_article .login .kakaologin .daumlogo{
  display: inline-block;
  margin-right: 4px;
  transform: translateY(10%);
}
.mainarticle .wrap .right_article .login .morelogin{
  width: 90%;
  display: flex;
  justify-content: space-between;
  font-size: 18px;
}
.mainarticle .wrap .right_article .login .morelogin .qr{
  display: inline-block;
  margin-right: 4px;
}
.mainarticle .wrap .right_article .advertise2{
  width: 100%;
  height: 150px;
  margin-top: 10px;
  border: 1px solid rgba(0,0,0,0.2);
  display: flex;
  justify-content: center;
  align-items: center;
}
.mainarticle .wrap .right_article .advertise2 .ad2Txt>div ,.mainarticle .wrap .right_article .advertise3 .ad2Txt>div{
  width: 60%;
  font-family: 'Cute Font', cursive;
  font-size: 24px;
  line-height: 25px;
  text-align: center;
  margin: 0 auto;
}
.mainarticle .wrap .right_article .advertise2 .ad2Txt button ,.mainarticle .wrap .right_article .advertise3 .ad2Txt button{
  width: 60%;
  background:none;
  border: 1px solid blue;
  color: skyblue;
  transform: translateX(35%);
}
.mainarticle .wrap .right_article .shopping{
  width: 100%;
  height: 780px;
  margin-top: 10px;
  border: 1px solid rgba(0,0,0,0.2);
}
.mainarticle .wrap .right_article .deal{
  width: 100%;
  height: 410px;
  margin-top: 10px;
  border: 1px solid rgba(0,0,0,0.2);
}
.mainarticle .wrap .right_article .advertise3{
  width: 100%;
  height: 150px;
  margin-top: 10px;
  border: 1px solid rgba(0,0,0,0.2);
  display: flex;
  justify-content: center;
  align-items: center;
}
/* ------ */
/* 오늘의 이미지 */
.todayImg{
  width: 100%;
  height: 400px;
  margin-bottom: 15px;
  background: rgba(128,128,128,0.06);
}
.todayImg .wrap{
  width: 1050px;
  height: 100%;
  margin: 0 auto;
  border: 1px solid rgb(128, 128, 128,0.2);
}
/* ------ */
/* 푸터 */
.footer{
  width: 100%;
  border-top: 1px solid black;
}
.footer .wrap{
  width: 900px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
}
.footer .wrap .notice{
  margin-top: 10px; 
  margin-bottom: 10px;
  font-family: 'Cute Font', cursive;
  font-size: 20px;
}
.footer .wrap .noticemain{float: left;}
.footer .wrap .noticemain>img{transform: translateY(35%);}
.footer .wrap .noticemain>a{margin-left: 10px;}
.footer .wrap .noticeetc{
  float: right;
}
.footer .wrap .noticeetc a{
  background: none;
  border: none;
  font-family: 'Cute Font', cursive;
  font-size: 20px;
  color: gray;
}
.footer .wrap .info{margin-bottom: 10px;}
.footer .wrap .info a{
  color: gray;
  font-size: 13px;
  margin-right: 10px;
}
.footer .wrap .info a:hover{text-decoration: underline;}
.footer .wrap .copyright{
  font-size: 12px;
  color: gray;
  margin-bottom: 10px;
}
</style>