<script>
// import MainCSS from "@/assets/main.css";
import RankingList from "@/components/homepage/RankingList.vue";
import HomeTitle from "@/components/homepage/HomeTitle.vue";
import CourseInfo from "@/components/homepage/CourseInfo.vue";
import AboutTeacher from "@/components/homepage/AboutTeacher.vue";
import StudentWork from "@/components/homepage/StudentWork.vue";
import RankingListTablet from "@/components/homepage/RankingListTablet.vue";
import ShakeBox from "@/components/homepage/HomePageShakeBox.vue";
// import blob1 from "@/assets/img/homepage/BGpictures/Vector1.svg";
// import blob2 from "@/assets/img/homepage/BGpictures/Vector2.svg";
// import blob3 from "@/assets/img/homepage/BGpictures/Vector3.svg";
import blob1 from "@/components/blob/blob1.vue";
import blob2 from "@/components/blob/blob2.vue";
import blob3 from "@/components/blob/blob3.vue";

// import TheWelcome from '../components/TheWelcome.vue'
export default {
  components: {
    RankingList,
    HomeTitle,
    AboutTeacher,
    CourseInfo,
    StudentWork,
    blob2,
    blob3,
    RankingListTablet,
    ShakeBox,
  },
  data() {
    return {
      WidthControl: "",
    };
  },
  mounted() {
    window.scrollTo(0, 0);
    this.$emit("ShakeBoxMobile_flagback", false);
  },
  methods: {
    // since1998
    scrollToLonger() {
      this.$refs.longerSlogn.scrollIntoView({ behavior: "smooth" });
    },

    handleImageEnter() {
      let dataToSend = "Hi";
      this.$emit("imageEnter", dataToSend);
    },
    handleImageLeave() {
      let dataToSend = "bYE";
      this.$emit("imageLeave", dataToSend);
    },
    handleCanClickE() {
      let dataToSend = "bE";
      this.$emit("handleCanClickE", dataToSend);
    },
    handleCanClickL() {
      let dataToSend = "bL";
      this.$emit("handleCanClickL", dataToSend);
    },

    // scrollTest() {
    //   console.log(this.$refs.longerSlogn.scrollTop);
    // },
  },
};
</script>

<template>
  <!-- <TheWelcome /> -->
  <main></main>
  <!-- banner -->
  <picture class="banner">
    <source
      media="(min-width:1800px)"
      srcset="@/assets/img/generic/banner-xl.png"
    />
    <source
      media="(min-width:1200px)"
      srcset="@/assets/img/generic/banner-xl.png"
    />
    <source
      media="(min-width:768px)"
      srcset="@/assets/img/generic/banner-xl.png"
    />
    <source
      media="(min-width:0px)"
      srcset="@/assets/img/generic/banner-sm.png"
    />
    <img
      @mouseenter="handleImageEnter"
      @mouseleave="handleImageLeave"
      src="@/assets/img/generic/banner-sm.png"
      alt="Weather"
    />
  </picture>
  <section class="position-container cursor-pointer">
    <div
      @mouseenter="handleCanClickE"
      @mouseleave="handleCanClickL"
      class="since1994 breathing flex flex-col gap-[10px]"
      @click="scrollToLonger"
    >
      <p>since 1994</p>
      <i class="fa-solid fa-chevron-down xl:text-[2.5rem] text-[1.25rem]"></i>
    </div>
  </section>
  <section class="longer-bg bg-MainColorBG">
    <section class="longer-introduce">
      <div class="longer-slogn" ref="longerSlogn">
        <p class="title">龍格畫室</p>
        <p class="content">一間成立於1994年的小畫室</p>
        <p class="content">位在三民路的小巷裡，由丁建中老師從零開始默默耕耘</p>
        <p class="content">至今已成為在地人口耳相傳的老字號畫室。</p>
      </div>
      <blob2 class="blob2"></blob2>
    </section>
  </section>

  <section>
    <HomeTitle class="bg-MainColorBG xl:pt-[60px] lg:pt-0 pt-[40px]"
      >關於龍格</HomeTitle
    >
    <AboutTeacher></AboutTeacher>
  </section>

  <section>
    <div class="Block4Top">
      <div class="Block4TopCurve"></div>
    </div>
    <div class="Block4">
      <HomeTitle class="xl:mt-[0px] lg:mt-[-200px]">課程資訊</HomeTitle>
      <CourseInfo
        @handleCourseCanClickE="handleCanClickE"
        @handleCourseCanClickL="handleCanClickL"
      ></CourseInfo>
      <div ref="Mask" class="pen">
        <!-- <div class="mask" :style="{ width: `${WidthControl}% ` }"></div> -->
      </div>

      <HomeTitle class="pt-[62px] md:pt-[0px]">學生作品</HomeTitle>
      <StudentWork></StudentWork>
    </div>
    <div class="Block4Buttom">
      <div class="Block4ButtomCurve"></div>
    </div>
  </section>

  <section class="bg-MainColorBG">
    <div class="Block5">
      <HomeTitle class="mt-[30px] md:mt-[0px]">歷年榜單</HomeTitle>
      <blob2 class="top-[1100px] left-[-30px] md:hidden"></blob2>
      <blob3 class="lg:top-[0px] lg:right-[-30px] lg:block hidden"></blob3>
      <RankingListTablet class="flex justify-center"></RankingListTablet>
      <RankingList></RankingList>
    </div>
    <div class="ShakeBox">
      <ShakeBox></ShakeBox>
    </div>
  </section>
  <section></section>
</template>
<style lang="scss" scoped>
// .Ranking {
//   @apply flex  align-center;
// }

.Ranking {
  @apply flex items-center h-[152px] w-[100%] bg-[MainColorBG];

  .text {
    // 第一行是所有文字外框都共用的樣式
    @apply flex items-center justify-center w-[300px] h-[72px] text-[3.25rem] bg-[url('@/assets/img/homepage/CommonIcon/YLdraw.svg')];
  }
}

.banner {
  img {
    @apply lg:h-[calc(100vh_-_120px)] md:h-auto h-[calc(100vh_-_60px)] w-full;
  }
}

// since-1994黃色小圓
.position-container {
  @apply relative;

  .since1994 {
    @apply z-[2] text-[#fff] bg-EmphasizeColor opacity-[0.7] rounded-full absolute xl:w-[170px] xl:h-[170px] lg:w-[114px] lg:h-[114px] w-[100px] h-[100px] flex justify-center items-center lg:text-[1.25rem] xl:text-[1.5rem] text-[1rem] xl:top-[-85px] lg:top-[-57px] top-[-50px] xl:left-[calc(50%_-_85px)] lg:left-[calc(50%_-_72px)] left-[calc(50%_-_50px)];
    // translate-x-[-50%]
  }
}

// 龍格畫室直式文字
.longer-introduce {
  @apply w-full flex justify-center relative text-[#fff] lg:bg-[url("@/assets/img/generic/longer-slogn-bg.svg")] md:bg-[url("@/assets/img/generic/longer-slogn-LG.svg")] bg-[url("@/assets/img/generic/longer-slogn-MD.svg")] xl:bg-cover md:bg-bottom bg-cover bg-top bg-no-repeat;

  .longer-slogn {
    // @apply absolute top-[0%] left-[60%];
    @apply xl:pt-[160px] xl:pl-[320px] lg:pt-[100px] lg:pl-[190px] md:pt-[80px] md:pl-[120px] pt-[90px] pl-[100px] xl:pb-[30px] pb-[60px];
    writing-mode: vertical-rl;

    .title {
      @apply xl:text-[4rem] lg:text-[2.69rem] lg:tracking-[20px] md:text-[1.62rem] md:tracking-[10px] text-[1.25rem] tracking-[10px] leading-[5];
    }

    .content {
      @apply xl:text-[2.5rem] xl:tracking-[6px] lg:text-[1.72rem] lg:tracking-[4px] md:text-[1rem] md:tracking-[2.8px] text-[0.87rem] tracking-[5px] xl:h-[150vh] leading-[2];
    }
  }

  .blob2 {
    @apply absolute xl:w-auto xl:top-[60%] lg:w-[300px] lg:top-[50%] md:w-[200px] md:top-[30%] md:left-[-10vh] w-[0px];
  }
}

// 區塊4的css
.bg-set {
  background: none;
  /* Add !important to override scoped styles */
  height: 72px;
  padding-left: calc(50% - 150px);
}

.Block4Top {
  @apply w-[100%] h-[289px] bg-MainColorBG;

  .Block4TopCurve {
    @apply w-[100%] h-[100%] bg-[url("@/assets/img/homepage/BGpictures/curve1.svg")] bg-no-repeat bg-cover;
  }
}

.Block4Buttom {
  @apply w-[100%] xl:h-[450px] md:h-[200px] h-[150px] bg-MainColorBG;

  .Block4ButtomCurve {
    @apply w-[100%] h-[100%] xl:bg-[url("@/assets/img/homepage/BGpictures/curve2.svg")] bg-[url("@/assets/img/homepage/BGpictures/curve2_laptop.svg")] bg-no-repeat bg-cover bg-center xl:mt-[-10px] lg:mt-[0px] md:mt-[-4px];
  }
}

.Block4 {
  @apply w-[100%] bg-MainColor overflow-hidden xl:h-[1375px] lg:h-[1260px] md:h-[1460px] h-[1905px];
}

// GSAP
.mask {
  @apply w-[120%] h-[480px] absolute bottom-0 right-[0px] rounded-l-[50%] bg-MainColor;
  --mask-width: 120%;
}

.Block5 {
  @apply w-[100%] h-[600px] xl:h-[1200px] lg:h-[1300px] md:h-[1000px] bg-MainColorBG relative overflow-hidden;
}

// 呼吸since1994
.breathing {
  animation: breathing 3s ease-in-out infinite normal;
  border-radius: 2px;
  text-align: center;
}

@keyframes breathing {
  0% {
    -webkit-transform: scale(0.9);
    -ms-transform: scale(0.9);
    transform: scale(0.9);
  }

  25% {
    -webkit-transform: scale(1);
    -ms-transform: scale(1);
    transform: scale(1);
  }

  60% {
    -webkit-transform: scale(0.9);
    -ms-transform: scale(0.9);
    transform: scale(0.9);
  }

  100% {
    -webkit-transform: scale(0.9);
    -ms-transform: scale(0.9);
    transform: scale(0.9);
  }
}

// 動來動去的盒子
.ShakeBox {
  @apply bg-MainColorBG bg-center flex justify-center;
}
</style>

<style>
#ShakeBoxId {
  display: none;
}
</style>
