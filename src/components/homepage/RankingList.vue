<script>
import BookCover from "@/assets/img/homepage/sign.png";
export default {
  data() {
    return {
      flag: false,
      img: BookCover,
      RankNumber: [
        {
          year: 106,
          details: [
            { name: "陳O瑩", school: "東海大學美術研究所" },
            { name: "蘇　O", school: "朝陽科技大學建築研究所" },
            { name: "林O安", school: "國立台北藝術大學動畫系" },
            { name: "何O聿", school: "國立台北藝術大學美術系" },
            { name: "黃O頤", school: "國立台灣藝術大學古蹟維護系" },
            { name: "劉O妤", school: "國立彰化師範大學美術系" },
            { name: "陳O禧", school: "國立台北教育大學藝術與造形設計學系" },
            { name: "趙O萱", school: "國立台北教育大學藝術與造形設計學系" },
            { name: "林O廷", school: "國立嘉義大學視覺藝術學系" },
          ],
        },
        {
          year: 105,
          details: [
            {
              name: "廖O輔",
              school: "國立新竹教育大學藝術與設計系創作組(素描90分彩繪90分)",
            },
            { name: "周O恩", school: "國立台南大學視覺藝術與設計系(創意93分)" },
            { name: "洪O昇", school: "國立嘉義大學視覺藝術系" },
            { name: "林O熙", school: "國立台科大工商業設計系(術科滿分)" },
            { name: "望O閔", school: "國立台科大建築系" },
            { name: "李O芳", school: "國立雲科大數位媒體設計系" },
            { name: "林O晟", school: "國立台中科大室內設計系" },
            { name: "廖O敏", school: "大同大學工業設計系" },
            { name: "楊O樂", school: "銘傳大學商品設計學系" },

            // ... (other data for year 105)
          ],
        },
        {
          year: 104,
          details: [
            {
              name: "林O珍",
              school: "台中教育大學美術系研究所",
            },
            {
              name: "劉O皓",
              school: "亞洲大學創意商品設計學系",
            },
            {
              name: "林O蓉",
              school: "台灣藝術大學美術系西畫組(素描90分)",
            },
            {
              name: "林O柔",
              school: "亞洲大學時尚設計學系 時尚精品設計組",
            },
            {
              name: "梁O韻",
              school: "國立台東大學美術產業學系(素描93分)",
            },
            {
              name: "王O程",
              school: "亞洲大學行動商務與多媒體應用學系多媒體應用組",
            },
            {
              name: "黃O賢",
              school: "國立台南藝術大學材質創作與設計學系",
            },
            {
              name: "張O堯",
              school: "亞洲大學 室內設計學系 住宅空間組",
            },
            {
              name: "吳O蓁",
              school: "台北醫學大學牙體技術學系",
            },
            {
              name: "葉O鈴",
              school: "朝陽科技大學 視覺傳達設計系",
            },

            // ... (other data for year 105)
          ],
        },
      ],
    };
  },
  mounted() {},
  methods: {
    VanishShadow() {
      console.log("翻書了");

      setTimeout(() => {
        this.flag = !this.flag;
      }, "500");
    },
  },
  computed: {},
};
</script>
<template>
  <div class="RankingBG">
    <div class="cover">
      <div class="book">
        <label for="page-1" class="book__page book__page--1">
          <img class="" src="@/assets/img/homepage/cover.png" alt="" />
        </label>

        <label for="page-2" class="book__page book__page--4">
          <!-- 我是第3頁 -->
          <div class="page__content truncate">
            <table>
              <thead>
                <tr>
                  <th>姓名</th>
                  <th>學校與系所</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in RankNumber[2].details" :key="item.id">
                  <td>{{ item.name }}</td>
                  <td>{{ item.school }}</td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="page__number">3</div>
        </label>

        <!-- Resets the page -->
        <input
          @change="VanishShadow()"
          class="PageTurn"
          type="radio"
          name="page"
          id="page-1"
        />

        <!-- Goes to the second page -->
        <input
          @change="VanishShadow()"
          class="PageTurn"
          type="radio"
          name="page"
          id="page-2"
        />
        <label class="book__page book__page--2">
          <div class="book__page-front">
            <!-- 暫時把多的切掉 -->
            <div class="page__content truncate">
              <!-- 我是第1頁 -->

              <table>
                <thead>
                  <tr>
                    <th>姓名</th>
                    <th>學校與系所</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="item in RankNumber[0].details" :key="item.id">
                    <td>{{ item.name }}</td>
                    <td>{{ item.school }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
          <div class="book__page-back">
            <div class="page__content">
              <!-- 我是第2頁 -->
              <div class="page__content truncate">
                <table>
                  <thead>
                    <tr>
                      <th>姓名</th>
                      <th>學校與系所</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr v-for="item in RankNumber[1].details" :key="item.id">
                      <td>{{ item.name }}</td>
                      <td>{{ item.school }}</td>
                    </tr>
                  </tbody>
                </table>
              </div>

              <div class="page__number">2</div>
            </div>
          </div>
        </label>
      </div>
      <transition>
        <RouterLink to="/admissionList" v-show="flag" class="navBar more"
          >更多優良榜單 ></RouterLink
        >
      </transition>
    </div>
    <!-- 更多 -->
  </div>
</template>
<style lang="scss" scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.3s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

// bg-[MainColorBG]
.RankingBG {
  @apply w-[100%]  bg-MainColorBG flex items-center justify-center xl:pt-[63px] lg:pt-[99px];

  .cover {
    @apply relative shadow-lg h-[647px] lg:block hidden;
  }
  // relative shadow-lg w-[1429px] h-[647px]

  // img {
  //   @apply border border-[rgba(0,0,0,0.06)] border-l-8;
  // }
  .cover:after {
    @apply xl:w-[150px] lg:w-[130px] md:w-[100px] w-[80px]
    top-[0px]
    xl:left-[660px] lg:left-[520px] md:left-[320px] left-[80px];
    content: "";
    display: block;

    height: 647px;
    background: linear-gradient(
      90deg,
      rgba(227, 225, 217, 0.02) 0%,
      rgba(208, 206, 198, 0.05) 10%,
      rgba(208, 206, 198, 0.08) 15%,
      rgba(121, 119, 116, 0.1) 25%,
      rgba(121, 119, 116, 0.25) 50%,
      rgba(121, 119, 116, 0.1) 75%,
      rgba(208, 206, 198, 0.08) 85%,
      rgba(208, 206, 198, 0.05) 90%,
      rgba(227, 225, 217, 0.02) 100%
    );
    position: absolute;
  }

  .cover:before {
    @apply xl:left-[660px] lg:left-[520px] md:left-[320px] left-[80px]
    xl:top-[580px] lg:top-[570px] md:top-[560px] top-[550px]
    xl:w-[100] lg:w-[80px] md:w-[60px] w-[50px]
    xl:h-[100] lg:h-[80px] md:h-[60px] h-[50px];
    content: "";
    display: block;
    width: 100px;
    height: 100px;
    background: #372011;
    position: absolute;
    border-radius: 50%;

    box-shadow: 10px 10px 10px rgba(0, 0, 0, 0.2);
  }

  .book {
    @apply border-8 border-[#56311a] shadow-2xl shadow-[#56331a] rounded-md;
  }

  table {
    border-collapse: collapse;

    th {
      width: 25vw;
      height: 75px;
    }

    td {
      width: 25vw;
      height: 50px;
      text-align: center;
    }
  }

  .more {
    @apply block bg-[#8a7c6b] p-6 absolute right-[-55px] top-[280px] rounded-lg text-[#FFFFFF] shadow-lg;
  }

  .more:hover {
    @apply bg-EmphasizeColor;
  }
}

// @import url("https://fonts.googleapis.com/css?family=Cormorant+Garamond:300,400,600|Tulpen+One&display=swap");

:root {
  /* spacing */
  /* this is what defines the global scale */
  --baseline: 12px;

  /* fonts */
  --book-title: "Tulpen One", sans-serif;
  --title: "Cormorant Garamond", serif;
  --body: "Cormorant Garamond", serif;
  --base-size: var(--baseline) * 1.2;
}

// body {
//   background-color: var(--body-bg);
//   height: 100vh;
//   display: flex;
//   flex-direction: column;
//   align-items: center;
//   justify-content: center;
// }

.book {
  @apply xl:w-[1429px] lg:w-[1150px] md:w-[700px];
  // 依設計大小
  height: 647px;
  display: flex;
  perspective: 1200px;

  &__page {
    position: relative;
    width: 50%;
    height: 100%;
    display: grid;
    transform: rotateY(0deg);
    transition: transform 0.9s cubic-bezier(0.645, 0.045, 0.355, 1);
    transform-origin: 0% 0%;
    background-color: var(--page-bg);
    background-image: linear-gradient(
      90deg,
      rgba(227, 227, 227, 1) 0%,
      rgba(249, 4, 4, 0) 18%
    );

    &:nth-of-type(1) {
      background-image: linear-gradient(
        -90deg,
        rgba(227, 227, 227, 1) 0%,
        rgba(247, 247, 247, 0) 18%
      );
    }

    // 封面圖片
    &--1 {
      cursor: pointer;
      overflow: hidden;

      img {
        // border-radius: 10%;
        width: 100%;
        // max-width: 100%;
        height: 100%;
      }
    }

    &--2 {
      position: absolute;
      right: 0;
      pointer-events: none;
      transform-style: preserve-3d;
      // background-color: var(--page-bg);

      background-image: linear-gradient(
        90deg,
        rgba(227, 227, 227, 1) 0%,
        rgba(247, 247, 247, 0) 18%
      );
    }

    &--4 {
      cursor: pointer;
      padding: 0 calc(var(--baseline) * 3);
    }

    &-front {
      position: absolute;
      width: 100%;
      height: 100%;
      transform: rotateY(0deg) translateZ(1px);
    }

    &-back {
      position: absolute;
      width: 100%;
      height: 100%;
      padding: 0 calc(var(--baseline) * 1.8);
      transform: rotateY(180deg) translateZ(1px);
    }

    // 內文的大小設定
    .page__content {
      // 可能要調整
      padding: 30px;
      height: 100%;
      position: relative;
      background-color: #f6f6f6;
      text-align: center;

      // box-shadow: 30px 0px 0px 0px rgba(0, 0, 0, 1);
      // &-book-title {
      //   font-family: var(--book-title);
      //   // font-size: calc(var(--base-size) * 3);
      //   font-weight: bold;
      //   text-transform: uppercase;
      //   letter-spacing: 3px;
      //   color: var(--dark-text);
      //   margin-top: calc(var(--baseline) * 5);
      //   margin-bottom: calc(var(--baseline) * 2);
      // }

      // &-author {
      //   font-family: var(--title);
      //   font-size: calc(var(--base-size) * 1.2);
      //   font-weight: 100;
      //   text-transform: uppercase;
      //   color: var(--dark-text);
      //   border-top: 1px solid var(--dark-text);
      //   border-bottom: 1px solid var(--dark-text);
      //   display: inline-block;
      //   padding: calc(var(--baseline) / 2) calc(var(--baseline) / 5);
      //   margin-bottom: calc(var(--baseline) * 6);
      // }

      // &-credits {
      //   font-family: var(--title);
      //   text-transform: uppercase;
      //   font-size: calc(var(--base-size) * 0.8);
      //   margin-bottom: calc(var(--baseline) * 2);
      //   letter-spacing: 1px;

      //   span {
      //     display: block;
      //     font-size: calc(var(--base-size) * 1.2);
      //     letter-spacing: 0;
      //   }
      // }

      // &-copyright {
      //   position: absolute;
      //   width: calc(100% - (var(--baseline) * 2));
      //   bottom: calc(var(--baseline) * 2);
      //   font-family: var(--title);
      //   font-size: calc(var(--base-size) * 0.8);
      //   text-transform: uppercase;
      // }

      // &-title {
      //   font-family: var(--title);
      //   font-size: calc(var(--base-size) * 1);
      //   text-transform: uppercase;
      //   letter-spacing: 1px;
      //   margin-top: calc(var(--baseline) * 5);
      //   margin-bottom: calc(var(--baseline) * 3);
      // }

      // &-table {
      //   width: 100%;
      //   margin-top: calc(var(--baseline) * 2);

      //   td {
      //     font-family: var(--title);
      //     font-size: calc(var(--base-size) * 1);
      //     padding-bottom: calc(var(--baseline) * 1.5);
      //     text-transform: uppercase;
      //   }
      // }

      // &-blockquote {
      //   margin-bottom: calc(var(--baseline) * 2);
      // }

      // &-blockquote-text {
      //   font-family: var(--title);
      //   font-size: calc(var(--base-size) * 0.67);
      //   font-style: italic;
      //   text-align: justify;
      // }

      // &-blockquote-reference {
      //   font-family: var(--title);
      //   font-size: calc(var(--base-size) * 0.7);
      //   margin-top: calc(var(--baseline) * 0.3);
      //   float: right;
      //   text-transform: uppercase;
      // }

      // &-text {
      //   font-family: var(--title);
      //   font-size: calc(var(--base-size) * 0.67);
      //   text-align: justify;
      //   text-indent: var(--baseline);
      // }
    }

    .page__number {
      position: absolute;
      bottom: var(--baseline);
      width: calc(100% - (var(--baseline) * 2));
      font-size: calc(var(--base-size) * 0.67);
      text-align: center;
    }
  }

  input[type="radio"] {
    display: none;

    &:checked + .book__page {
      transition: transform 0.9s cubic-bezier(0.645, 0.045, 0.355, 1);
      transform: rotateY(-180deg);
    }
  }
}
</style>
