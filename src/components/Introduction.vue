<template>
    <v-app>
      <!-- Hero Section -->
      <v-container fluid>
        <v-row align="center" justify="center" class="text-center">
          <v-col cols="12">
            <h1 class="hero-title">MMFC Introduction</h1>
            <h2 class="hero-subtitle">比赛细节和规则</h2>
          </v-col>
        </v-row>
      </v-container>
  
      <!-- Introduction Section -->
      <v-container class="my-10">
        <v-row>
          <v-col cols="12" v-for="section in sections" :key="section.title">
            <v-card class="section-card" outlined>
              <v-card-title class="section-title">{{ section.title }}</v-card-title>
              <v-card-text v-html="section.content" class="section-content"></v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-app>
  </template>
  
  <script>
  export default {
    name: "CompetitionIntroduction",
    data: () => ({
      sections: [
        {
          title: "比赛概述",
          content: "MMFC（每月一次的写谱竞赛）是一个面向全球maimai自制谱创作人员的比赛。不局限于上机标准，旨在提升自制谱质量、挖掘新的创作者。比赛以“日常向”和“非强制”为关键词，采用动态积分制排名。"
        },
        {
          title: "比赛规则",
          content: "- 选曲通常限于几首，甚至一首完整版歌曲。<br>- 谱面创作规定为standard/DX/无限制三大类，频率各异。<br>- 规模一般在100-200人之间，已成为华语maimai谱面创作圈最大型的比赛。"
        },
        {
          title: "海选和评审",
          content: "- 海选由高水平谱师和前排选手组成，对初次提交作品进行投票。<br>- 达到指定票数的作品进入正赛，通常约60个作品。<br>- 比赛结果未公布前，严禁将参赛作品传播到公共平台。"
        },
        {
          title: "比赛流程和时间安排",
          content: "- 制作阶段：2-3周，月初或月末宣布主题和规定。<br>- 筛选阶段：1.5周，从海选库中挑选作品。<br>- 评审阶段：1.5周，作品评分。<br>- 结果公布：公布积分总结和奖励。"
        },
        {
          title: "报名与提交要求",
          content: "- 报名通过邮箱或问卷进行。<br>- 作品提交需在3周内完成，遵循simai语法规范。<br>- 比赛是否定期举行存在疑问，评审期可能与下一次制作阶段重合。"
        },
        {
          title: "奖励与认证",
          content: "- 比赛结果和积分将发布在专门的网站上。<br>- 网站功能包括评论和添加个人页面，作为谱师的信息展示。"
        },
        // 可以添加更多部分
      ],
    }),
  };
  </script>
  
  <style>
.hero-title {
  font-family: 'Noto Sans SC', sans-serif;
  font-size: 3.5rem;
  color: #1976D2;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.hero-subtitle {
  font-family: 'Noto Sans SC', sans-serif;
  font-size: 2rem;
  color: #424242;
  margin-bottom: 2rem;
}

.section-card {
  margin: 1.5rem 0;
  border-color: #E0E0E0;
}

.section-title {
  font-family: 'Noto Sans SC', sans-serif;
  font-size: 2rem;
  color: #1E88E5;
}

.section-content {
  font-family: 'Roboto', sans-serif;
  font-size: 1.2rem;
  color: #333;
  line-height: 1.6;
}
</style>