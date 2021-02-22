<template>
  <div>
    <h3>基于艾洛积分系统（Elo Rating System）修改</h3>
            <h4>1、所有用户初试得分1500</h4>
            <h4>2、题目难度分为简单1000，中等1500，困难2000</h4>
            <h4>3、在规定时间内答题，每次失败提交减去20分提交，以提交中最好的成绩为准</h4>
            <h4>      最后得分为提交后的分数/测试用例总数 * 通过的测试点数</h4>
            <h4>4、若挑战别人成功，获得1000分，否则，减去500分</h4>
            <h4>5、若用户提供出算法的正确测试用例，则奖励2000分</h4>

            <h3>不同积分显示的颜色如下：</h3>
            <el-table
              :data="RatingData"
              border
              style="width: 70%"
              size="mini"
              :row-style="rankcolor"
            >
              <el-table-column prop="name" label="Name"></el-table-column>
              <el-table-column prop="rating" label="Score"></el-table-column>
              <el-table-column prop="color" label="Color"></el-table-column>
            </el-table>
  </div>
</template>

<script>
export default {
  name: "ratingrule",
  data() {
    return {RatingData: [
        { name: "Legendary Grandmaster", rating: "3000+", color: "红色" },
        {
          name: "International Grandmaster",
          rating: "2600 ~ 2999",
          color: "褐色"
        },
        { name: "Grandmaster", rating: "2200 ~ 2599", color: "橙色" },
        { name: "International master", rating: "2050 ~ 2199", color: "紫色" },
        { name: "Master", rating: "1900 ~ 2049", color: "蓝色" },
        { name: "Candidate master", rating: "1700 ~ 1899", color: "青色" },
        { name: "Expert", rating: "1500 ~ 1699", color: "绿色" },
        { name: "Specialist", rating: "1350 ~ 1499", color: "草绿色" },
        { name: "Pupil", rating: "1200 ~ 1349", color: "灰色" },
        { name: "Newbie", rating: "0 ~ 1199", color: "黑色" }
      ]};
  },
  methods:{
      rankcolor({ row, rowIndex }) {
      if (rowIndex == 0) return "color:red;font-weight: bold;";
      if (rowIndex == 1) return "color:#BB5E00;font-weight: bold;";
      if (rowIndex == 2) return "color:#E6A23C;font-weight: bold;";
      if (rowIndex == 3) return "color:#930093;font-weight: bold;";
      if (rowIndex == 4) return "color:#0000AA;font-weight: bold;";
      if (rowIndex == 5) return "color:#007799;font-weight: bold;";
      if (rowIndex == 6) return "color:#227700;font-weight: bold;";
      if (rowIndex == 7) return "color:#67C23A;font-weight: bold;";
      if (rowIndex == 8) return "color:#909399;font-weight: bold;";
      return "color:#303133;font-weight: bold;";
    },
  }
};
</script>

<style  scoped>
</style>