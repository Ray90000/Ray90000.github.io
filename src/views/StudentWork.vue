<script>
import HomeTitle from "@/components/homepage/HomeTitle.vue";

// 導入lightbox
import lightbox from "lightbox2";
// 導入圖片-素描
import sketch01 from "@/assets/img/student_work/sketch_img/sketch_01.jpg";
import sketch02 from "@/assets/img/student_work/sketch_img/sketch_02.jpg";
import sketch03 from "@/assets/img/student_work/sketch_img/sketch_03.jpg";
import sketch04 from "@/assets/img/student_work/sketch_img/sketch_04.jpg";
import sketch05 from "@/assets/img/student_work/sketch_img/sketch_05.jpg";
import sketch06 from "@/assets/img/student_work/sketch_img/sketch_06.jpg";
// 導入圖片-水彩類
import waterColor01 from "@/assets/img/student_work/water_color_img/water_color_01.jpg";
import waterColor02 from "@/assets/img/student_work/water_color_img/water_color_02.jpg";
import waterColor03 from "@/assets/img/student_work/water_color_img/water_color_03.jpg";
import waterColor04 from "@/assets/img/student_work/water_color_img/water_color_04.jpg";
import waterColor05 from "@/assets/img/student_work/water_color_img/water_color_05.jpg";
import waterColor06 from "@/assets/img/student_work/water_color_img/water_color_06.jpg";
import waterColor07 from "@/assets/img/student_work/water_color_img/water_color_07.jpg";
import waterColor08 from "@/assets/img/student_work/water_color_img/water_color_08.jpg";
import waterColor09 from "@/assets/img/student_work/water_color_img/water_color_09.jpg";
import waterColor10 from "@/assets/img/student_work/water_color_img/water_color_10.jpg";
import waterColor11 from "@/assets/img/student_work/water_color_img/water_color_11.jpg";
import waterColor12 from "@/assets/img/student_work/water_color_img/water_color_12.jpg";
// 導入圖片-水墨
import ink01 from "@/assets/img/student_work/ink_img/ink_01.jpg";
import ink02 from "@/assets/img/student_work/ink_img/ink_02.jpg";
import ink03 from "@/assets/img/student_work/ink_img/ink_03.jpg";
import ink04 from "@/assets/img/student_work/ink_img/ink_04.jpg";
import ink05 from "@/assets/img/student_work/ink_img/ink_05.jpg";
import ink06 from "@/assets/img/student_work/ink_img/ink_06.jpg";
import ink07 from "@/assets/img/student_work/ink_img/ink_07.jpg";
// 導入圖片-色鉛筆
import coloredPencil01 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_01.jpg";
import coloredPencil02 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_02.jpg";
import coloredPencil03 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_03.jpg";
import coloredPencil04 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_04.jpg";
import coloredPencil05 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_05.jpg";
import coloredPencil06 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_06.jpg";
import coloredPencil07 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_07.jpg";
import coloredPencil08 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_08.jpg";
import coloredPencil09 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_09.jpg";
import coloredPencil10 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_10.jpg";
import coloredPencil11 from "@/assets/img/student_work/colored_pencils_img/colored_pencils_11.jpg";
// 導入圖片-麥克筆
import marker01 from "@/assets/img/student_work/marker_img/marker_01.png";
import marker02 from "@/assets/img/student_work/marker_img/marker_02.png";
import marker03 from "@/assets/img/student_work/marker_img/marker_03.jpg";
import marker04 from "@/assets/img/student_work/marker_img/marker_04.jpg";
import marker05 from "@/assets/img/student_work/marker_img/marker_05.png";
import marker06 from "@/assets/img/student_work/marker_img/marker_06.jpg";
import marker07 from "@/assets/img/student_work/marker_img/marker_07.jpg";
import marker08 from "@/assets/img/student_work/marker_img/marker_08.jpg";
import marker09 from "@/assets/img/student_work/marker_img/marker_09.jpg";
// 導入圖片-炭筆
import charcoal01 from "@/assets/img/student_work/charcoal_img/charcoal_01.jpg";
import charcoal02 from "@/assets/img/student_work/charcoal_img/charcoal_02.jpg";
import charcoal03 from "@/assets/img/student_work/charcoal_img/charcoal_03.jpg";
import charcoal04 from "@/assets/img/student_work/charcoal_img/charcoal_04.jpg";
import charcoal05 from "@/assets/img/student_work/charcoal_img/charcoal_05.jpg";
import charcoal06 from "@/assets/img/student_work/charcoal_img/charcoal_06.jpg";
import charcoal07 from "@/assets/img/student_work/charcoal_img/charcoal_07.jpg";
import charcoal08 from "@/assets/img/student_work/charcoal_img/charcoal_08.jpg";
// 導入圖片-石膏素描
import plaster01 from "@/assets/img/student_work/plaster_img/plaster_01.jpg";
import plaster02 from "@/assets/img/student_work/plaster_img/plaster_02.jpg";
import plaster03 from "@/assets/img/student_work/plaster_img/plaster_03.jpg";
import plaster04 from "@/assets/img/student_work/plaster_img/plaster_04.jpg";
import plaster05 from "@/assets/img/student_work/plaster_img/plaster_05.jpg";

// 導入圖片-兒童美術
import childArt01 from "@/assets/img/student_work/child_art_img/child_art_01.jpg";
import childArt02 from "@/assets/img/student_work/child_art_img/child_art_02.jpg";
import childArt03 from "@/assets/img/student_work/child_art_img/child_art_03.jpg";
import childArt04 from "@/assets/img/student_work/child_art_img/child_art_04.jpg";
import childArt05 from "@/assets/img/student_work/child_art_img/child_art_05.jpg";
import childArt06 from "@/assets/img/student_work/child_art_img/child_art_06.jpg";
import childArt07 from "@/assets/img/student_work/child_art_img/child_art_07.jpg";
import childArt08 from "@/assets/img/student_work/child_art_img/child_art_08.jpg";
import childArt09 from "@/assets/img/student_work/child_art_img/child_art_09.jpg";
import childArt10 from "@/assets/img/student_work/child_art_img/child_art_10.jpg";
// 粉彩
import pastel01 from "@/assets/img/student_work/pastel_img/pastel_01.jpg";
import pastel02 from "@/assets/img/student_work/pastel_img/pastel_02.jpg";
// 背景圖
import bg01 from "@/assets/img/student_work/bg-1.svg";
import bg02 from "@/assets/img/student_work/bg-2.png";
import bg03 from "@/assets/img/student_work/bg-3.png";
// blob 動圖
// import blob2 from "@/components/blob/blob2.vue";
// import blob3 from "@/components/blob/blob3.vue";

export default {
  // components: { HomeTitle, blob2, blob3 },
  components: { HomeTitle },
  data() {
    return {
      bg01,
      bg02,
      bg03,

      studentWorks: [
        {
          skill: "素描",
          dataText: "sketch",
          img: [sketch01, sketch02, sketch03, sketch04, sketch05, sketch06],
        },
        {
          skill: "水彩",
          dataText: "waterColor",
          img: [
            waterColor01,
            waterColor02,
            waterColor03,
            waterColor04,
            waterColor05,
            waterColor06,
            waterColor07,
            waterColor08,
            waterColor09,
            waterColor10,
            waterColor11,
            waterColor12,
          ],
        },
        {
          skill: "水墨",
          dataText: "ink",
          img: [ink01, ink02, ink03, ink04, ink05, ink06, ink07],
        },
        {
          skill: "色鉛筆",
          dataText: "coloredPencil",
          img: [
            coloredPencil01,
            coloredPencil02,
            coloredPencil03,
            coloredPencil04,
            coloredPencil05,
            coloredPencil06,
            coloredPencil07,
            coloredPencil08,
            coloredPencil09,
            coloredPencil10,
            coloredPencil11,
          ],
        },
        {
          skill: "麥克筆",
          dataText: "marker",
          img: [
            marker01,
            marker02,
            marker03,
            marker04,
            marker05,
            marker06,
            marker07,
            marker08,
            marker09,
          ],
        },
        {
          skill: "炭筆靜物",
          dataText: "charcoal",
          img: [
            charcoal01,
            charcoal02,
            charcoal03,
            charcoal04,
            charcoal05,
            charcoal06,
            charcoal07,
            charcoal08,
          ],
        },
        {
          skill: "石膏素描",
          dataText: "plaster",
          img: [plaster01, plaster02, plaster03, plaster04, plaster05],
        },
        {
          skill: "兒童美術創意",
          dataText: "childArt",
          img: [
            childArt01,
            childArt02,
            childArt03,
            childArt04,
            childArt05,
            childArt06,
            childArt07,
            childArt08,
            childArt09,
            childArt10,
          ],
        },
        {
          skill: "粉彩",
          dataText: "pastel",
          img: [pastel01, pastel02],
        },
      ],
    };
  },

  mounted() {
    window.scrollTo(0, 0);

    lightbox.option({
      resizeDuration: 500,
      wrapAround: true,
    });
    this.$emit("ShakeBoxMobile_flagback", true);
  },
};
</script>
<template>
  <NavCurve class="md:block hidden"> </NavCurve>
  <NavMobile class="md:hidden block"></NavMobile>
  <main>
    <HomeTitle
      class="xl:!justify-start xl:pl-[138px] xl:mb-[134px] md:mb-[96px] mb-[87px]"
      >學生作品</HomeTitle
    >
    <!-- <blob2 class="top-[-5%] right-[-5%]"></blob2>
    <blob3 class="bottom-[0%] left-[-5%]"></blob3> -->
    <!-- 背景圖片 -->
    <img :src="bg01" alt="background01" class="bg bg01" />
    <section>
      <section>
        <div
          class="box"
          v-for="item in studentWorks"
          :key="item.id"
          v-fade-in-out
        >
          <a
            class="image-link"
            v-for="imgItem in item.img"
            :key="imgItem.id"
            :href="imgItem"
            :data-lightbox="item.dataText"
            :data-title="item.skill"
          >
            <div
              class="image"
              :style="{ backgroundImage: `url(${imgItem})` }"
            ></div>
            <div class="mask">{{ item.skill }}</div>
          </a>
        </div>
      </section>
    </section>
  </main>
</template>
<style lang="scss" scoped>
main {
  @apply pt-0 relative bg-MainColorBG overflow-hidden;

  .HomeTitle {
    @apply pt-[93px] pb-[168px] relative left-[213px];
  }

  .bg {
    @apply absolute;
  }

  .bg01 {
    @apply bottom-[0%] right-0;
  }

  .bg02 {
    @apply top-0 right-0 z-0;
  }

  .bg03 {
    @apply bottom-[-40px] left-0;
  }

  section {
    @apply flex lg:justify-center md:justify-start justify-center items-start w-full xl:pt-[127px] pt-0 pb-[282px];

    section {
      @apply flex flex-wrap xl:gap-[60px] gap-[47px] xl:max-w-[1270px] lg:max-w-[913px] max-w-[593px] mx-[auto] pt-0 pb-0;

      .box {
        @apply flex items-center xl:w-[380px] xl:h-[380px] w-[273px] h-[273px] relative overflow-hidden;

        .image-link {
          &:not(:first-child) {
            @apply hidden;
          }

          .image {
            @apply xl:translate-x-0 translate-x-[-60px] w-[380px] h-[380px] bg-no-repeat bg-cover opacity-[0.8] hover:scale-[1.25] duration-[1s];
          }
        }

        .mask {
          @apply w-full py-[10px] xl:text-[1.75rem] text-[1.25rem] text-center text-[#fff] font-sans bg-[#000] opacity-[0.8] absolute xl:top-[84%] top-[82%];
        }
      }
    }
  }
}
</style>
