<template>
  <div class="TvOne">
      <div class="container">
          <div class="item">
            <div class="imgdeco">
              <span class="imginfo">그림자 미녀</span>
              <img class="TvImg" src="../Image/TV/tv1.png" alt="">
              <img class="videoImg" src="../Image/video.png" alt="동영상 재생" width="20px" height="20px">
            </div>
            <span id="title">너무 리얼한 엑스트라 연기에 <br>그만</span>
          </div>
          <div class="item">
            <div class="imgdeco">
              <span class="imginfo">송경아 타임즈</span>
              <img class="TvImg" src="../Image/TV/tv2.png" alt="">
              <img class="videoImg" src="../Image/video.png" alt="동영상 재생" width="20px" height="20px">
            </div>
            <span id="title">허리가 편하다는 200만원 의자</span>
          </div>
     
          <div class="item">
            <div class="imgdeco">
              <span class="imginfo">초아</span>
              <img class="TvImg" src="../Image/TV/tv3.png" alt="">
              <img class="videoImg" src="../Image/video.png" alt="동영상 재생" width="20px" height="20px">
            </div>
            <span id="title">점 보다가 본인 성격 틀킨 <br>연예인</span>
          </div>
          <div class="item">
            <div class="imgdeco">
              <span class="imginfo">펌킨타임</span>
              <img class="TvImg" src="../Image/TV/tv4.png" alt="">
              <img class="videoImg" src="../Image/video.png" alt="동영상 재생" width="20px" height="20px">
            </div>
            <span id="title">오해를 불러일으킨 과거 <br>사진</span>
            <!-- <img class="videoImg" src="../Image/video.png" alt="동영상 재생" width="20px" height="20px"> -->
          </div>
      </div>
  </div>
</template>

<script>
export default {

};
</script>

<style scoped>
.TvOne{
  width: 100%;
  height: 100%;
}
.TvOne .container{
  margin-left: 20px;
  margin-right: 20px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
.TvOne .container .item .imgdeco{
  position: relative;
}
.TvOne .container .item{
  height: 135px;
  overflow: hidden;
  margin-bottom: 5px;
}
.TvOne  .container .item .TvImg{
  width: 100%;
  height: 80px;
}
.TvOne .container .item .TvImg:hover{cursor: pointer;}
.TvOne  .container .item #title{
    width: 75%;
    height: 35px;
    margin: 0 auto;
    display: block;
    font-size: 15px;
    font-family: 'Cute Font', cursive;
}
.container .item:hover>#title, .TvOne .container .item .lists #artiLists:hover{text-decoration: underline;color:#01C1FA; cursor: pointer;}
.imgdeco .imginfo{
  position: absolute;
  top: 0;
  left: 0;
  font-family: 'Cute Font', cursive;
  background:black;
  color: white;
  padding-left: 4px;
  padding-right: 4px;
}
.imgdeco .imginfo:hover{cursor: pointer;}
.imgdeco .videoImg{
  position: absolute;
  right: 0;
  bottom: 0;
  transform: translateX(-50%) translateY(-50%);
  filter: invert(100%);
}
.TvOne .container .item .lists{
  display: flex;
  flex-direction: column;
}
.TvOne .container .item .lists #artiLists{
  width: 95%;
  font-size: 20px;
  margin-top: 0.5px;
}
.TvOne .container .item .lists #artiLists #critical{
  color: red;
  font-weight: 600;
  display: inline-block;
  margin-right: 2px;
}
</style>
