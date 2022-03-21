<template>
  <div class="StoryOne">
      <div class="container">
          <div class="item">
            <img class="TvImg" src="../Image/Story/story2.png" alt="">
            <span id="title">손흥민에게 인사를 건낸 <br>아기</span>
            <span id="addinfo">樂soccer</span>
          </div>
          <div class="item">
            <img class="TvImg" src="../Image/Story/story1.png" alt="">
            <span id="title">???쟤는 못보던 엔시틴데?</span>
            <span id="addinfo">소울드레서</span>
          </div>
          <div class="item">
             <div class="lists">
                <div id="artiLists"><span>교수님 진짜로 올빼미가 과제를 찢었다니까요!!</span></div>
                <div id="artiLists"><span>헤이즈가 고치기 힘들어했던 사투리</span></div>
                <div id="artiLists"><span>군대 가기 전 미리 알고 크리스탈이랑 통화하는 공명</span></div>
                <div id="artiLists"><span>벨트 없을때 꿀팁</span></div>
                <div id="artiLists"><span>헤어진 전 여친이 넷플릭스를 공짜로 쓴 방법</span></div>
                <div id="artiLists"><span>서울 지하철의 결점</span></div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {

};
</script>

<style scoped>
.StoryOne{
  width: 100%;
  height: 100%;
}
.StoryOne .container{
  margin-left: 20px;
  margin-right: 20px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
.StoryOne .container .item .imgdeco{
  position: relative;
}
.StoryOne .container .item{
  height: 135px;
  overflow: hidden;
  margin-bottom: 5px;
}
.StoryOne  .container .item .TvImg{
  width: 100%;
  height: 80px;
}
.StoryOne .container .item .TvImg:hover{cursor: pointer;}
.StoryOne  .container .item #title{
    width: 75%;
    margin: 0 auto;
    display: block;
    font-size: 15px;
    font-family: 'Cute Font', cursive;
}
.StoryOne  .container .item #addinfo{
  width: 75%;
  height: 10px;
  margin: 0 auto;
  display: block;
  font-size: 15px;
  color: gray;
  font-family: 'Cute Font', cursive;
}
.container .item:hover>#title, .StoryOne .container .item .lists #artiLists:hover{text-decoration: underline;color:#01C1FA; cursor: pointer;}

.StoryOne .container .item .lists{
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.StoryOne .container .item .lists #artiLists{
  font-size: 17.5px;
  margin-top: 0.5px;
  font-family: 'Cute Font', cursive;
  text-indent: 10px;
  line-height: 17px;
  letter-spacing:1.5px
}
.item:nth-child(3){
  grid-column: 3 / span 2;
	grid-row: 1 / span 1;
  background:rgba(128,128,128,0.1);
  border: 1px solid rgba(0,0,0,0.1);
}
</style>
