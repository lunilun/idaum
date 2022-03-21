<template>
  <div class="shop">

    <div class="shopHeader">
      <div class="title">
        <a href=""><span>쇼핑<span id="snapper">＞</span></span></a>
      </div>
      <div class="company">
        <a href="" class="gmarket"><img src="../Image/Shopping/gmarket.png" alt="G마켓" width="25px" height="25px"><span id="inner">G마켓</span></a>
        <a href="" class="oction"><img src="../Image/Shopping/oction.png" alt="옥션" width="25px" height="25px"><span id="inner">옥션</span></a>
      </div>
    </div>

    <div class="shopCate">
      <ul>
        <!-- 각 행 마지막 특수문자 지워야되는데 -->
        <li v-for="(i,index) in lists" v-bind:key="index"><a href="">{{i}}</a><span id="circle"> &#183; </span></li>
      </ul>
    </div>


    <div class="shopitems">

      <div class="tagradio">
        <div class="buttons">
          <button @click="radioPre">◁</button>
          <button @click="radioNext">▷</button>
        </div>
          <div class="counting">
          {{count}}/{{18}}
        </div>
      </div>

      <div class="itemExample">
        <div class="item">
            <img class="EtcImg" src="../Image/Items/item1 .png" alt="">
            <span id="title">쫀득쫀득 美친 그맛 반값일 때 사먹어봐</span>
          </div>  
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item2 .png" alt="">
            <span id="title">백년묵은 각질 사르르 시원하게</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item3 .png" alt="">
            <span id="title">세트지오후드패딩5만원대하루특가</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item4 .png" alt="">
            <span id="title">에디션外신상.새해맞이85%↓</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item5 .png" alt="">
            <span id="title">코트+밴딩팬츠.합리적인 가격</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item6 .png" alt="">
            <span id="title">따뜻한 겨울 sale.52%↓특가중!</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item7 .png" alt="">
            <span id="title">+야들야들한 소갈비+. 2+2가 2만원대</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item8 .png" alt="">
            <span id="title">따뜻한 겨울이불.48% 특가할인</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item9 .png" alt="">
            <span id="title">1만원 이상 전상품 무료배송</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item10 .png" alt="">
            <span id="title">제주 비트 무료배송 5Kg 1만원대</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item11 .png" alt="">
            <span id="title">최고의 가방 SALE 50%</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Items/item12 .png" alt="">
            <span id="title">컬럼비아 특가. 최대 91% 할인</span>
          </div>
      </div>
          
    </div>
    
   
  </div>
</template>

<script>
export default {
  components:{
  },
  data(){
    return{
      count:1,
      lists:[
        "하프클럽","쿠팡","11번기","GS샵","패션플러스","리빙픽",
        "깔끔대장","아이스탁몰","티나티나","뮬리안","첵시믹스",
        "마이더스비","마이쥬","투게더","모놀로그","조아맘"
      ],
    }
  },
  methods:{
    radioPre(){
      this.count--;
      if(this.count<=0) this.count = 18;
    },
    radioNext(){
      this.count++;
      if(this.count>18) this.count = 1;
    },
  },
};
</script>

<style scoped>
.shop{
  width: 100%;
  height: 100%;
}
.shop .tagMenu{
  width: 100%;
  height: 40px;
  align-items: center;
  justify-content: space-between;
}
.shop .shopHeader{
  width: 100%;
  height: 50px;
  background:rgba(128,128,128,.2);
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Cute Font', cursive;
  font-size: 25px;
}
.shop .shopHeader .title{margin-left: 10px;}
.shop .shopHeader .company a{display: inline-block; margin-right: 10px;}
.shop .shopHeader .company a:hover>span, .shop .shopCate a:hover{text-decoration: underline; color:#01C1FA}
.shop .shopHeader .company a>img{margin-right: 3px; transform: translateY(25%);}
#snapper{font-size: 13px;}
#circle{font-size: 20px;}

.shop .shopCate ul{padding-left: 0; margin-left: 12px;}
.shop .shopCate li{
  display: inline-block;
  font-family: 'Cute Font', cursive;
  font-size: 19px;
}

.shop .shopitems{
  display: flex;
  flex-direction: column;
}
.shop .shopitems .tagradio{margin-right: 10px;}
.shop .shopitems .tagradio .buttons button{
  background:white;
  border: 1px solid rgba(128,128,128,0.5);
}
.shop .shopitems .tagradio div{
  display: block;
  float: right;
  margin-right: 5px;
  font-family: 'Cute Font', cursive;
  font-size: 20px;
}

.shop .shopitems .itemExample{
  margin-left: 10px;
  margin-right: 10px;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 5px;
  margin-top: 10px;
}
.shop .shopitems .itemExample .item{
  height: 135px;
  margin-bottom: 5px;
}
.shop .shopitems .itemExample .item .EtcImg{
  width: 100%;
  height: 100px;
}
.shop .shopitems .itemExample .item span{
  width: 90%;
  height: 35px;
  margin: 0 auto;
  overflow:hidden; 
  text-overflow: ellipsis; 
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  font-size: 15px;
  font-family: 'Cute Font', cursive;
}
.shop .shopitems .itemExample .item:hover{cursor: pointer;}
.shop .shopitems .itemExample .item:hover>span{text-decoration: underline;color:#01C1FA; cursor: pointer;}
</style>
