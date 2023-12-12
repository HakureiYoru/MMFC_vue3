<template>
  <v-container>
    <!-- Ad Banner Section -->
    <v-carousel cycle hide-delimiters height="400">
      <v-carousel-item v-for="(slide, i) in slides" :key="i">
        <v-img
          :src="slide.src"
          height="400"
          gradient="to bottom, rgba(0,0,0,.4), rgba(0,0,0,.7)"
          class="fill-height image-top-align"
          cover
        >
          <v-card
            class="ad-text-card"
            :class="{ 'elevation-2': slide.elevated }"
            absolute
            centered
          >
            <v-card-text>
              {{ slide.text }}
            </v-card-text>
            <v-card-actions>
              <v-btn color="primary" @click="navigateTo(slide.link)">
                Learn More
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-img>
      </v-carousel-item>
    </v-carousel>
    
    <!-- Welcome Section -->
    <v-row justify="center">
      <v-col cols="12" sm="8" md="6">
        <v-card>
          <v-img
            src="/welcome.jpg"
            height="300px"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            class="white--text align-end image-hover"
            alt="Welcome Image"
          >
            <v-card-title class="custom-title animated-title">
              欢迎来到MMFC
            </v-card-title>
          </v-img>
          <v-card-text>
            <p>This is a short introduction or welcome message.</p>
          </v-card-text>
          <v-card-actions>
            <router-link to="/introduction">
              <template v-slot:default="{ navigate }">
                <v-btn color="primary" @click="navigate">Introduction</v-btn>
              </template>
            </router-link>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>












<script>
export default {
  name: "WelcomePage",
  data() {
    return {
      slides: [
        { src: "/welcome_adv/1.jpg", text: "MMFC1", link: "/link1" },
        { src: "/welcome_adv/2.jpg", text: "MMFC2", link: "/link2" },
        { src: "/welcome_adv/3.jpg", text: "MMFC3", link: "/link3" },
        // 更多图片...
      ],
    };
  },

  methods: {
    navigateTo(link) {
      this.$router.push(link);
    },
  },
};
</script>

<style>
.fill-height .v-image__image {
  object-fit: cover; /* This ensures the image covers the area */
  object-position: top; /* This aligns the image to the top */
}

.custom-title {
  color: #ffffff; /* 更深的字体颜色，以提高对比度 */
  font-family: "Roboto", sans-serif; /* 一个现代、清晰的字体 */
  font-weight: bold; /* 加粗字体 */
  font-size: 2em; /* 增大字体大小 */
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); /* 添加文本阴影以提高可读性 */
}

/* 图像悬停放大效果 */
.image-hover:hover {
  transform: scale(1.05);
  transition: transform 0.5s ease;
}

/* 文本动画效果 */
@keyframes fadeInUp {
  from {
    transform: translateY(20px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.animated-title {
  animation: fadeInUp 1s ease-out;
}

.v-carousel-item .v-img {
  position: relative;
  height: 100%;
}



.ad-text-card {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 10px; /* Adjust padding as needed */
  border-radius: 80px; /* Optional: if you want rounded corners */
  background-color: rgba(255, 255, 255, 0.5); /* Semi-transparent white background */
  max-width: 80%; /* Or any max-width as per your design requirement */
}


.image-top-align .v-image__image {
  object-position: center top; /* 使图片的顶部与容器顶部对齐 */
}
</style>
