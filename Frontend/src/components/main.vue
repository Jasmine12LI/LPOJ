<template>
  <el-row :gutter="12">
    <el-col :span="6">
      <el-row :gutter="10">
        <topuser></topuser>
      </el-row>
      <el-row :gutter="10">
        <ojmessage></ojmessage>
      </el-row>
      <!-- <el-row :gutter="10">
        <cfrate></cfrate>
      </el-row> -->
    </el-col>
    <el-col :span="18">
      <!-- <soulrow></soulrow> -->
    
      <el-row>
        <el-tabs type="border-card">
          <el-tab-pane :label="label.des" >
            <description></description>
          </el-tab-pane>
          <el-tab-pane :label="label.rank" :lazy="true">
            <rankchart></rankchart>
          </el-tab-pane>
          <el-tab-pane :label="label.rule" :lazy="true">
            <ratingrule></ratingrule>
          </el-tab-pane>
        </el-tabs>
      </el-row>
     
    </el-col>
  </el-row>
</template>

<script>
import rankchart from "@/components/chart/rankchart";
import ojmessage from "@/components/utils/ojmessage";
import topuser from "@/components/utils/topuser";
import ratingrule from "@/components/utils/ratingrule";
import description from "@/components/utils/description";
import cfrate from "@/components/utils/cfrate";
export default {
  components: {
    rankchart,
    ojmessage,
    topuser,
    ratingrule,
    description,
    cfrate
  },
  name: "homepage",
  data() {
    return {
      label: {
        rank: "排名",
        team: "Team",
        rule: "规则",
        des: "详情"
      },

    };
  },
  mounted() {

  },
  methods: {
 
  }
};
</script>

<style scoped>
.el-row {
  margin-bottom: 12px;
}

</style>
