<script>
  import { Tabs, Tab, TabList, TabPanel } from 'svelte-tabs'
  // @ts-ignore
  import { Button } from 'svelte-mui'

  let eventsData = [
    {
      event: '(백제) 근초고왕 즉위',
      year: 346
    },
    {
      event: '(고구려) 광개토왕 즉위',
      year: 391
    },
    {
      event: '(신라) 진흥왕 즉위',
      year: 540
    },
    {
      event: '살수대첩 (을지문덕)',
      year: 612
    },
    {
      event: '안시성 전투 (양만춘 - 당나라)',
      year: 645
    },
    {
      event: '삼국 통일 (신라 문무왕)',
      year: 676
    },
    {
      event: '발해 건국 (대조영)',
      year: 698
    },
    {
      event: '고려 건국 (왕건)',
      year: 918
    },
    {
      event: '발해 멸망 (거란 친입)',
      year: 926
    },
    {
      event: '이자겸의 난 (외척 세력)',
      year: 1126
    },
    {
      event: '묘청의 난 (서경천도운동)',
      year: 1135
    },
    {
      event: '무신 정변 (문벌귀족 붕괴)',
      year: 1170
    },
    {
      event: '몽골 1차 친입 (원나라)',
      year: 1231
    },
    {
      event: '팔만대장경 완성 (해인사 보관)',
      year: 1251
    },
    {
      event: '직지심체요절 (금속활자본)',
      year: 1377
    },
    {
      event: '조선건국 (명나라)',
      year: 1392
    },
    {
      event: '훈민정음 창제',
      year: 1443
    },
    {
      event: '훈민정음 반포',
      year: 1446
    },
    {
      event: '임진왜란',
      year: 1592
    },
    {
      event: '정유재란',
      year: 1597
    },
    {
      event: '왜란 종료',
      year: 1598
    },
    {
      event: '병자호란',
      year: 1636
    },
    {
      event: '대동법 시행 (특산물 - 쌀로 납세 통일)',
      year: 1708
    },
    {
      event: '정조 즉위',
      year: 1776
    },
    {
      event: '홍경래의 난 (평안도 농민 항쟁)',
      year: 1811
    },
    {
      event: '흥선대원권 집권',
      year: 1863
    },
    {
      event: '병인양요 (쇄국 강화)',
      year: 1866
    },
    {
      event: '신미양요 (쇄국 강화)',
      year: 1871
    },
    {
      event: '강화도 조약 (조일수호조규)',
      year: 1876
    },
    {
      event: '임오군란 (구식군대 병란)',
      year: 1882
    },
    {
      event: '갑신정변 (급진개화파)',
      year: 1884
    },
    {
      event: '방곡령 (콩 해외 유출 금지령)',
      year: 1889
    },
    {
      event: '동학 농민 운동 (반봉건, 반외세)',
      year: 1894
    },
    {
      event: '갑오개혁 (=갑오경장, 친일 개화)',
      year: 1894
    },
    {
      event: '청일 전쟁 (조선 지배권 쟁탈)',
      year: 1894
    },
    {
      event: '을미사변 (명성왕후 시해)',
      year: 1895
    },
    {
      event: '아관파천 (1년간 러 간섭)',
      year: 1896
    },
    {
      event: '독립신문 창간 (독립협회)',
      year: 1896
    },
    {
      event: '대한제국 수립 (고종 황제)',
      year: 1897
    },
    {
      event: '경인선 철도 개통 (최초 철도)',
      year: 1899
    },
    {
      event: '러일전쟁 (한국/만주 지배권 쟁탈)',
      year: 1904
    },
    {
      event: '을사조약 (외교권 박탈)',
      year: 1905
    },
    {
      event: '국채보상운동 (대구 1300만원)',
      year: 1907
    },
    {
      event: '신민회 (서울, 비밀결사)',
      year: 1907
    },
    {
      event: '헤이그 특사 (이상설, 이준, 이위종)',
      year: 1907
    },
    {
      event: '안중근 의거 (만주 하얼빈역)',
      year: 1909
    },
    {
      event: '한일합방 (경술국치)',
      year: 1910
    },
    {
      event: '토지조사사업 (조선총독부)',
      year: 1912
    },
    {
      event: '31운동 (기미년, 거족적)',
      year: 1919
    },
    {
      event: '상해임시정부 (대통령 이승만)',
      year: 1919
    },
    {
      event: '조선 동아일보 창간',
      year: 1920
    },
    {
      event: '봉오동 청산리 전투',
      year: 1920
    },
    {
      event: '신간회 (서울, 좌우익 합작)',
      year: 1927
    },
    {
      event: '중일전쟁 (2차대전 종료까지)',
      year: 1937
    },
    {
      event: '창씨개명 (창씨 의무, 개명 자유)',
      year: 1940
    },
    {
      event: '태평양 전쟁 (진주만 기습)',
      year: 1941
    },
    {
      event: '조선어학회 사건 (민족말살)',
      year: 1942
    },
    {
      event: '징병제 학병제',
      year: 1943
    },
    {
      event: '8. 15. 해방 (히로시마, 나가사키 원폭)',
      year: 1945
    },
    {
      event: '모스크바 3상회의 (미영소)',
      year: 1945
    },
    {
      event: '헌법 공포 7.17.',
      year: 1948
    },
    {
      event: '대한민국정부 수립 (8. 15.)',
      year: 1948
    },
    {
      event: '조선민주주의인민공화국 수립 (9. 9.)',
      year: 1948
    },
    {
      event: '한국전쟁 (6. 25.)',
      year: 1950
    },
    {
      event: '휴전협정',
      year: 1953
    },
    {
      event: '4.19. 혁명 (반 이승만 독재)',
      year: 1960
    },
    {
      event: '5.16. 군사정변 (박정희)',
      year: 1961
    },
    {
      event: '한일협정 (한일국교 재개)',
      year: 1965
    },
    {
      event: '베트남 파병',
      year: 1965
    },
    {
      event: '경부고속도로 개통 (박정희)',
      year: 1970
    },
    {
      event: '10. 26. 사태 (박정희 살해)',
      year: 1979
    },
    {
      event: '5. 18. 광주민주화 운동',
      year: 1980
    },
    {
      event: '6월 민주항쟁 (직선제 개헌)',
      year: 1987
    },
    {
      event: '제 24회 서울올림픽',
      year: 1988
    },
    {
      event: 'IMF 외환위기 (구제금융)',
      year: 1997
    }
  ]

  let orderStart = false
  let randomStart = false

  let inOrder = false
  let inRandom = false
  let OrderAnswer = false
  let RandomAnswer = false
  let OrderIndex = 0

  let textEventOrder = ''
  let textYearOrder = ''
  let textEventRandom = ''
  let textYearRandom = ''

  const StartOrder = () => {
    inOrder = true
    orderStart = true
    OrderNext()
  }

  const StartRandom = () => {
    inRandom = true
    randomStart = true
    RandomNext()
  }

  const ShowOrder = () => {
    OrderAnswer = true
  }

  const ShowRandom = () => {
    RandomAnswer = true
  }

  const OrderNext = () => {
    let random = eventsData[OrderIndex++]

    textEventOrder = random.event
    textYearOrder = random.year
    OrderAnswer = false

    if (OrderIndex >= eventsData.length) {
      OrderIndex = 0
    }
  }

  const RandomNext = () => {
    let random = eventsData[Math.floor(Math.random() * eventsData.length)]

    textEventRandom = random.event
    textYearRandom = random.year
    OrderAnswer = false
  }

  let count = 0

  const Following = () => {
    count++

    if (count % 2 == 0) {
      if (orderStart) ShowOrder()
      if (randomStart) ShowRandom()
    } else {
      if (orderStart) OrderNext()
      if (randomStart) RandomNext()
    }
  }

  window.addEventListener('keydown', function (e) {
    if (e.keyCode === 32 || e.keycode === 13) Following()
  })
</script>

<div class="special" on:touchstart="{Following}">
  <Tabs>
    <TabList>
      <Tab>연도 순서대로</Tab>
      <Tab>연도 무작위로</Tab>
    </TabList>

    <TabPanel>
      {#if !inOrder}
      <div class="card">
        <div class="card__content">
          <div class="card__content__title">
            <h2>연도 순서대로</h2>
          </div>
          <div class="card__content__body">
            <div>
              <p>연도를 순서대로로 묻는 문제입니다.</p>
            </div>
            <div class="card__content__body__button">
              <Button on:click="{StartOrder}">시작</Button>
            </div>
          </div>
        </div>
      </div>
      {:else}
      <div class="card">
        <div class="card__content">
          <div class="card__content__title">
            <h2>{textEventOrder}</h2>
          </div>
          <div class="card__content__body">
            <div class="card__content__body__text">
              {#if OrderAnswer}
              <p>{textYearOrder}</p>
              {/if}
            </div>
          </div>
        </div>
      </div>
      {/if}
    </TabPanel>

    <TabPanel>
      {#if !inRandom}
      <div class="card">
        <div class="card__content">
          <div class="card__content__title">
            <h2>연도 무직위로</h2>
          </div>
          <div class="card__content__body">
            <div>
              <p>연도를 무작위로 묻는 문제입니다.</p>
            </div>
            <div class="card__content__body__button">
              <Button on:click="{StartRandom}">시작</Button>
            </div>
          </div>
        </div>
      </div>
      {:else}
      <div class="card">
        <div class="card__content">
          <div class="card__content__title">
            <h2>{textEventRandom}</h2>
          </div>
          <div class="card__content__body">
            <div class="card__content__body__text">
              {#if OrderAnswer}
              <p>{textYearRandom}</p>
              {/if}
            </div>
          </div>
        </div>
      </div>
      {/if}
    </TabPanel>
  </Tabs>
</div>

<style>
  .card__content__body__button {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
  }

  .card__content__body__text > p {
    font-size: 70px !important;
  }
</style>
