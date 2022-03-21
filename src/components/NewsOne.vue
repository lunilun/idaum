<template>
  <div class="NewsOne">
    <!-- 남은 태그들 어떻게 할지 생각해보기 -->
      <div class="container">
          <div class="item">
            <img class="newImg" src="../Image/news/new1.png" alt="">
            <span id="title">태양 10억배 에너지 0.1초간 방출..중성자별 '마그네타' 포착</span>
          </div>
          <div class="item">
            <img class="newImg" src="../Image/news/new2.png" alt="">
            <span id="title">월세 밀려 가보니 고양이 수십마리가 바글바글. 대체 무슨일이?</span>
          </div>
          <div class="item" id="not">
            <div class="lists">
              <div id="artiLists"><span id="critical">속보</span><span>윤석열'2030에 실망준 행보 깊이 반성 다른모습 보여주겠다</span></div>
              <div id="artiLists"><span>김종인"尹"약속도 안지킨 사람.쿠데타?그정도 판단이면</span></div>
              <div id="artiLists"><span>국민의 힘 보좌진들 '모두 손잡고 죽자는 기세' 이대로면 필</span></div>
              <div id="artiLists"><span>이제명 탈모 공약에 조국 '히트작' 이상이 교수'경알 할"</span></div>
              <div id="artiLists"><span>오스템임플란트"1800억 횡령 머리숙여 사과, 현금 풍부 24</span></div>
            </div>
          </div>
          <div class="item">
            <img class="newImg" src="../Image/news/new3.png" alt="">
            <span id="title">꼭짓점 찍었다는 강북 VS 연일 신고가 강남..두 얼굴의 서울아파트</span>
          </div>
          <div class="item">
            <img class="newImg" src="../Image/news/new4.png" alt="">
            <span id="title">한보그룹 부도 이후 폐가로, 분양으로 쪼개진 태백 한보사택</span>
            <img class="videoImg" src="../Image/video.png" alt="동영상 재생" width="20px" height="20px">
          </div>
            <div class="item" id="not">
               <div class="lists">
                <div id="artiLists"><span>"당직은 내가 임명" 버티는 이준석. 김재원 "자진사퇴 안하면</span></div>
                <div id="artiLists"><span>김주하 앵커는 왜 사실과 다른 자극적 질문 던졌나</span></div>
                <div id="artiLists"><span>김종인 "듯이 안맞으면 헤어지는 것" 尹과 결별 공식화</span></div>
                <div id="artiLists"><span>신성범.최택용.박원석 "내통은 후보책임 그러나 후보교체</span></div>
                <div id="artiLists"><span>오스템임플란트 3000억 대출한 은행권. 신용등급 재평가</span></div>
              </div>
            </div>
          <div class="item">
            <img class="newImg" src="../Image/news/new5.png" alt="">
            <span id="title">日 기시다 내각 경제안보 설계자 "가치관 다른 나라에 인프라 의존은 위험"</span>
          </div>
          <div class="item">
            <img class="newImg" src="../Image/news/new6.png" alt="">
            <span id="title">세련된 컴팩트 모델, 이보크 P250 R</span>
          </div>
            <div class="item" id="not">
               <div class="lists">
                <div id="artiLists"><span>70mm막대 엽기 살인범. 119 신고때 폭행 숨긴채 "어떡하지?"</span></div>
                <div id="artiLists"><span>김건희, 큐레이터 경력 아에 없었나?.. 미술관 직원들 '본</span></div>
                <div id="artiLists"><span>폭설도 80km 마비된 美고속도로. 영하에  24시간 넘게</span></div>
                <div id="artiLists"><span>김종인 "尹, 그 정도 정치 판단 능력이면 뜻 같이 할 수 없다"</span></div>
                <div id="artiLists"><span>美인형업체. 中소녀 모델로 '올해의 인형' 출시'亞인종차</span></div>
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
.NewsOne{
  width: 100%;
  height: 100%;
}
.NewsOne .container{
  margin-left: 20px;
  margin-right: 20px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
.NewsOne .container .item{
  height: 135px;
  overflow: hidden;
  margin-bottom: 5px;
  /* border: 1px solid black; */
}
.NewsOne  .container .item .newImg{
  width: 100%;
  height: 80px;
}
.NewsOne .container .item .newImg:hover{cursor: pointer;}
.NewsOne  .container .item #title{
  /* 멀티라인 */
    width: 80%;
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
.container .item:hover>#title, .NewsOne .container .item .lists #artiLists:hover{text-decoration: underline;color:#01C1FA; cursor: pointer;}
.item:nth-child(3){
	grid-column: 3 / span 2;
	grid-row: 1 / span 1;
}
.item:nth-child(6){
	grid-column: 3 / span 2;
	grid-row: 2 / span 1;
}
.item:nth-child(9){
	grid-column: 3 / span 2;
	grid-row: 3 / span 1;
}
.item:nth-child(5) .videoImg{
  position: absolute;
  transform: translateX(130px) translateY(-65px);
  filter: invert(100%);
}
.NewsOne .container .item .lists{
  display: flex;
  flex-direction: column;
}
.NewsOne .container .item .lists #artiLists{
  width: 95%;
  font-family: 'Cute Font', cursive;
  font-size: 20px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  margin-top: 0.5px;
}
.NewsOne .container .item .lists #artiLists #critical{
  color: red;
  font-weight: 600;
  display: inline-block;
  margin-right: 2px;
}
</style>
