<template>
  <div class="EtcOne">
      <div class="container">
          <div class="item">
            <div class="imgdeco">
              <img class="EtcImg" src="../Image/Etc/etc1.png" alt="">
              <span id="in_title1">&nbsp;브런치by스텔라</span>
              <span id="in_title2"><br>&nbsp;&nbsp;세상에서 가장 사랑스러운 침입자</span>
            </div>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/TV/tv2.png" alt="">
            <span id="title">허리가 편하다는 200만원<br>의자</span>
            <span id="addinfo">송경아타임즈</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Etc/etc2.png" alt="">
            <span id="title">카카오 뭘 냈다! 가성비<br>넘치는 무선이어폰</span>
            <span id="addinfo">리빙픽</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Etc/etc3.png" alt="">
            <span id="title">혼자 병원가기 어려울때,<br>'병원안심동행서비스'를</span>
            <span id="addinfo">서울씨</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Etc/etc4.png" alt="">
            <span id="title">새해 결심,'금연'.작심삼일<br>안되려면(리빙톡)</span>
            <span id="addinfo">연합뉴스</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Etc/etc5.png" alt="">
            <span id="title">겨울이면 걱정되는 낙상<br>사고.어떻게 예방할까?</span>
            <span id="addinfo">하이닥</span>
          </div>
          <div class="item">
            <img class="EtcImg" src="../Image/Etc/etc6.png" alt="">
            <span id="title">나의 소울푸드</span>
            <span id="addinfo">브런치by아란</span>
          </div>
      </div>
      <div class="best">
        <span class="title">베스트</span>
        <div class="bcontainer">
          <div class="bitem">
            <div class="bimgdeco">
              <img class="bEtcImg" src="../Image/Etc/etc7.png" alt="">
              <span id="bin_title1">&nbsp;아내의 가방</span>
            </div>
          </div>
          <div class="bitem">
            <div class="bimgdeco">
              <img class="bEtcImg" src="../Image/Etc/etc8.png" alt="">
              <span id="bin_title1">&nbsp;&nbsp;바세린을 설탕과</span>
              <span id="bin_title2"><br>&nbsp;&nbsp;섞으면 깜짝 놀랄거예요!</span>
            </div>
          </div>
          <div class="bitem">
            <li v-for="(i,index) in item_lists" v-bind:key="index">
                <div class="data_items">
                    <div class="data_no">{{i.no}}</div>
                    <div class="data_content">{{i.content}}</div>
                </div>
            </li>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      item_lists:[
        {no:1,  content:'의외로 한국인들이 실수하는 세탁법3'},
        {no:2,  content:'복도식 아프트에서의 겨울나기'},
        {no:3,  content:'조인성.송중기.리차드 기어까지 집으로 초대한다.'},
        {no:4,  content:'20년 함께한 부부의 흔한 대화'},
        {no:5,  content:'친정엄마의 손녀딸 머리부심'},
      ],
    }
  },
};
</script>

<style scoped>
li{
    list-style: none;
}
.EtcOne{
  width: 100%;
  height: 100%;
}
.EtcOne .container{
  margin-left: 20px;
  margin-right: 20px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
.EtcOne .container .item .imgdeco, .EtcOne .best .bimgdeco{
  position: relative;
}
.EtcOne .container .item{
  height: 135px;
  overflow: hidden;
  margin-bottom: 5px;
}
.EtcOne  .container .item .EtcImg:not(.item:nth-child(1) .EtcImg){
  width: 100%;
  height: 80px;
}
.EtcOne .container .item .EtcImg:hover, .bimgdeco{cursor: pointer;}
.EtcOne  .container .item #title{
  width: 75%;
  margin: 0 auto;
  display: block;
  font-size: 15px;
  font-family: 'Cute Font', cursive;
}
.EtcOne  .container .item #addinfo{
  width: 75%;
  height: 10px;
  margin: 0 auto;
  display: block;
  font-size: 15px;
  color: gray;
  font-family: 'Cute Font', cursive;
}

.container .item:hover>#title, .EtcOne .container .item .lists #artiLists:hover{text-decoration: underline;color:#01C1FA; cursor: pointer;}
.data_items:hover{cursor: pointer;}
.data_items:hover>.data_content{text-decoration: underline;color:#01C1FA; cursor: pointer;}

.EtcOne .container .item .lists{
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.EtcOne .container .item .lists #artiLists{
  font-size: 17.5px;
  margin-top: 0.5px;
  font-family: 'Cute Font', cursive;
  text-indent: 10px;
  line-height: 17px;
  letter-spacing:1.5px
}
.item:nth-child(1){
  grid-column: 1 / span 2;
	grid-row: 1 / span 1;
}
.item:nth-child(1) .EtcImg{
  width: 100%;
  height: 135px;
}
.item:nth-child(1) span{
  position: absolute;
  bottom: 0;
  left: 0;
  height: 40px;
  line-height: 20px;
  margin-bottom: 20px;
  color: white;
  font-family: 'Cute Font', cursive;
  font-size: 20px;
}

.EtcOne .best{
  height: 170px;
  margin-top: 10px;
  background: rgba(128,128,128,0.1);
  font-family: 'Cute Font', cursive;
  padding: 5px;
}
.EtcOne .best .title{
  font-size: 25px;
  margin-left: 20px;
}
.EtcOne .best .bcontainer{
  margin-left: 20px;
  margin-right: 20px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
.bitem .bEtcImg{
  width: 100%;
  height: 135px;
}
.bitem:nth-child(3){
  grid-column: 3 / span 4;
	grid-row: 1 / span 1;
}
.bitem:nth-child(1) span, .bitem:nth-child(2) span{
  position: absolute;
  bottom: 0;
  left: 0;
  height: 40px;
  line-height: 20px;
  color: white;
  font-family: 'Cute Font', cursive;
  font-size: 18px;
}
.bitem:nth-child(1) span{text-indent: 10px;}
.bitem:nth-child(2) span{margin-bottom: 10px;}
.data_items{
  display: flex;
  justify-content: flex-start;
  align-items: center;
  line-height: 25px;
  margin-left: 10px;
  font-size: 21px;
}
.data_items .data_no{
  width: 20px;
  height: 20px;
  background: gray;
  border-radius: 3px;
  margin-right: 10px;
  color: white;
  text-align: center;
}
</style>
