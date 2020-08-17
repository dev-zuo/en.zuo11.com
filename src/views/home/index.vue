<template>
  <!-- 首页 -->
  <div>
    <ul @click="gotoSubjectDetail">
      <li
        v-for="(subject, index) in subjectList"
        :key="subject.title"
        :data-index="index"
      >
        {{ subject.title }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      subjectList: []
    };
  },

  created() {
    this.getSubjectList();
  },

  methods: {
    getSubjectList() {
      this.subjectList = [
        {
          title: "The Inventor of LED",
          type: "readJudge",
          typeDesc: "阅读判断"
        },
        {
          title: "Skyscrapers and Environment",
          type: "readSelect",
          typeDesc: "阅读选择"
        }
      ];
    },
    gotoSubjectDetail(e) {
      let { index } = e.target.dataset;

      this.$router.push({
        name: "SubjectDetail",
        params: { detail: this.subjectList[index], index: index } // 参数，url上面不可见
        // query: { plan: "private" } // 查询参数 url上可见
      });
    }
  }
};
</script>

<style lang="less" scoped></style>
