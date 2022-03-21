<template>
  <div class="hotdeal">

    <div class="dealHeader">
      <div class="title">
        <a href=""><span>쇼핑몰 할인특가</span></a>
    </div>

    <div class="tagradio">
        <div class="buttons">
          <button @click="radioPre">◁</button>
          <button @click="radioNext">▷</button>
        </div>
          <div class="counting">
          {{count}}/{{6}}
        </div>
      </div>
    </div>

    <div class="hotCate" v-if="showCate">
      <a href="" class="wemepu">위메프&#183;위메프 추천상품</a>
      <a href="" class="gonow">바로가기</a>
    </div>

    <div class="hotitems">
      <ul>
        <li>
          <div class="hots">
            <div class="hotTxt">집에서 즐기는 향긋한 커피한잔<br>캡슐 커피머신 리스트</div>
            <img src="../Image/Hot/hot1.png" alt="상품 이미지1" width="80px" height="55px">
          </div>
        </li>
        <li>
          <div class="hots">
            <div class="hotTxt">감사함을 전하는 명절 3만원<br>미만 화장품 선물세트 추천</div>
            <img src="../Image/Hot/hot2.png" alt="상품 이미지2" width="80px" height="55px">
          </div>
        </li>
        <li>
          <div class="hots">
            <div class="hotTxt">22SS 신상도 있어요! 로고가<br>돋보이는 생로랑 가방</div>
            <img src="../Image/Hot/hot3.png" alt="상품 이미지3" width="80px" height="55px">
          </div>
        </li>
        <li>
          <div class="hots">
            <div class="hotTxt">홈카페처럼 꾸며보는 인테리어<br>감각적 디자인 의자</div>
            <img src="../Image/Hot/hot4.png" alt="상품 이미지4" width="80px" height="55px">
          </div>
        </li>
      </ul>
    </div>
    
    <div class="hotfooter">
        <div><button class="">쇼핑홈</button></div>
        <div><button class="">핫딜</button></div>
        <div><button class="">BEST 100</button></div>
    </div>
   
  </div>
</template>

<script>
export default {
  data(){
    return{
      showCate:true,
      count:1,
    }
  },
  methods:{
    radioPre(){
      this.count--;
      if(this.count<=0) this.count = 6;
    },
    radioNext(){
      this.count++;
      if(this.count>6) this.count = 1;
    },
  },
};
</script>

<style scoped>
ul{padding-left: 0;}
.hotdeal{
  width: 100%;
  height: 100%;
}
.hotdeal .tagMenu{
  width: 100%;
  height: 40px;
  align-items: center;
  justify-content: space-between;
}
.hotdeal .dealHeader{
  width: 100%;
  height: 50px;
  background:rgba(128,128,128,.2);
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Cute Font', cursive;
  font-size: 25px;
}
.hotdeal .dealHeader .title{margin-left: 10px;}

.hotdeal .tagradio{margin-right: 10px;}
.hotdeal .tagradio .buttons button{
  background:white;
  border: 1px solid rgba(128,128,128,0.5);
  color: skyblue;
}
.hotdeal .tagradio div{
  display: block;
  float: right;
  margin-right: 5px;
  font-family: 'Cute Font', cursive;
  font-size: 20px;
}
.hotdeal .hotCate{
  width: 100%;
  height: 30px;
  margin-top: 5px;
}
.hotdeal .hotCate a{
  font-family: 'Cute Font', cursive;
  font-size: 20px;
}
.hotdeal .hotCate .wemepu{
  float: left;
  margin-left: 10px;
}
.hotdeal .hotCate .gonow{
  float: right;
  margin-right: 10px;
}
.hotdeal .hotCate a:hover, .hotdeal .hotfooter div button:hover{text-decoration: underline;color:#01C1FA;}
.hotdeal .hotitems .hots{
  width: 90%;
  height: 55px;
  margin: 0 auto;
  margin-bottom: 5px;
}
.hotdeal .hotitems .hots image{float: left;}
.hotdeal .hotitems .hots .hotTxt{
  float: right;
  width: 160px;
  height: 55px;
  font-family: 'Cute Font', cursive;
  font-size: 17px;
  transform: translateY(10%);
  text-align: left;
}
.hotdeal .hotitems .hots:hover{cursor: pointer;}
.hotdeal .hotitems .hots:hover>.hotTxt{text-decoration: underline;color:#01C1FA;}
.hotdeal .hotfooter{
  width: 90%;
  height: 40px;
  margin: 0 auto;
}
.hotdeal .hotfooter div{
  display: inline-block;
  width: 88px;
  height: 100%;
}
.hotdeal .hotfooter div>button{
  width: 100%;
  height: 100%;
  background: white;
  border: 1px solid rgba(128,128,128,0.5);
  font-family: 'Cute Font', cursive;
  font-size: 20px;
}
.hotdeal .hotfooter div:nth-child(2){
  margin-left: 0.5px;
  margin-right: 0.5px;
}

</style>
