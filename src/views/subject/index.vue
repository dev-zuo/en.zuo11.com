<template>
  <!-- 首页 -->
  <div>
    <div class="top">
      <h1>{{ subjectDetail.title || "-" }}</h1>
      <div class="info">
        <el-tag size="mini">{{ subjectDetail.typeDesc }}</el-tag>
      </div>
    </div>
    <div class="container">
      <article class="article">
        <section
          v-for="paragraph in subjectDetail.paragraphs"
          :key="paragraph.content"
          class="paragraph-sec"
        >
          {{ paragraph.content }}
        </section>
      </article>
      <aside class="aside">
        <div>
          <el-button @click="showAnswer" type="primary" size="mini">
            提交答案
          </el-button>
        </div>
        <div
          v-for="(exercises, index) in subjectDetail.exercisesArr"
          :key="exercises.content"
        >
          <p>{{ index + 1 }}. {{ exercises.content }}</p>
          {{ exercises.result }}
          <div style="margin-left:10px;line-height: 40px;">
            <el-radio-group v-model="exercises.radio">
              <el-radio label="A">A. True</el-radio>
              <el-radio label="B">B. False</el-radio>
              <el-radio label="C">C. Not Given</el-radio>
            </el-radio-group>
          </div>
        </div>
      </aside>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      subjectDetail: {}
    };
  },

  created() {
    let { index, detail } = this.$route.params;
    console.log(index, detail);
    this.getSubjectDetail();
  },

  methods: {
    getSubjectDetail() {
      this.subjectDetail = {
        title: "The Inventor of LED",
        type: "readJudge",
        typeDesc: "阅读判断",
        paragraphs: [
          {
            content: `
              When Nick Holonyak set out to create a new kind of visible lighting using semiconductor(半导体) alloys(合金), his colleagues thought he was unrealistic. 
              Today, his discovery of light-emitting diodes, or LEDs, is used in everything from DVDs to alarm clocks to airports.
              Dozens of his students have continued his work, developing lighting used in traffic lights and other everyday technology.
              `
          },
          {
            content: `
              On April 23, 2004, Holonyak received the $500,000 Lemelson-MIT Prize at a ceremony in Washington. 
              This marks the 10th year that the Lemelson-MIT Program at the Massachusetts Institute of Technology(MIT) has given the award to prominent inventors.
             `
          },
          {
            content: `"Anytime you get an award, big or little, it's always a surprise." Holonyak said.`
          },
          {
            content: `
              Holonyak, 75, was a student of John Bardeen, an inventor of the transistor(晶体管), in the early 1950s.
              After graduate school, Holonyak worked at Bell Labs, He later went to General Electric, where he ivented a switch now widely used in house dimmer switches.
              Later, Holonyakk started looking into how semiconductors could be used to genertate light.
              But while his colleagues were looking into how to generate invisible light, he wanted to generate visible light.
              The LEDs he invented in 1962 now last about 10 times longer than incandescent bulbs, and are more environmentally friendly and cost effective.
            `
          },
          {
            content: `
              Holonyak, now a professor of electrical and computer engineerning and physics at the University of Illinois, said he suspected that LEDs would become as commonplace(平凡的) as they are today, but didn't realize how many uses the would have.
            `
          },
          {
            content: `
              "You don't konw in the begining. You think you're doing something important, you think it's worth doing, but you really can't tell what the big payoff(成果) is going to be, and how. You just dont't konw," he said.
            `
          },
          {
            content: `
              The Lemelson-MIT Program also recognized Edith Flanigen, 75, with the $100,000 Lemelson-MIT Lifetime Achievement Award for the work on a new generation of "nolecular(分子) sieves(滤网)" that can separate molecules by size.
            `
          }
        ],
        exercisesArr: [
          {
            content: `Holonyak's colleagues thought he would fail in his research on LEDs at the time when he started it.`,
            radio: "",
            result: "A",
            analysis: "我是分析"
          },
          {
            content: `Holonyak believed that his students that were working with him on the project would get the Lemelson MIT Prize sooner or later.`,
            radio: ""
          },
          {
            content: `Holonyak was the inventor of transisitor in the early 1950s`,
            radio: ""
          },
          {
            content: `LEDs used in traffic lights are developed by  Holonyak's students.`,
            radio: ""
          },
          {
            content: `When Holonyak invented LEDs, he belived that they would have a wide range of uses.`,
            radio: ""
          },
          {
            content: `Holonyak said that you should not do anything you are not interested in.`,
            radio: ""
          },
          {
            content: `LEDs are more environmentally friendly than incandescent bulbs.`,
            radio: ""
          },
          {
            content: `Holonyak was surprised to receive the Lemelson-MIT Prize.`,
            radio: ""
          },
          {
            content: `Edith Flanigen was also awarded Lemelson-MIT Prize for his work on LEDs`,
            radio: ""
          },
          {
            content: `The Lemeson-MIT Prize has a history of over 100  years.`,
            radio: ""
          }
        ]
      };
    },
    showAnswer() {
      this.$message.info("show answer");
    }
  }
};
</script>

<style lang="less" scoped>
.top {
  display: flex;
  align-items: center;
  padding: 0 20px;
  .info {
    margin-left: 10px;
  }
}
.container {
  display: flex;
  padding: 0 20px 20px;
  .article {
    width: 60%;
    box-sizing: border-box;
    padding-right: 20px;
    .paragraph-sec {
      text-indent: 2em;
      line-height: 30px;
      // 设置字母间距，仿语雀
      letter-spacing: 0.05em;
    }
  }
  .aside {
    width: 40%;
    p {
      margin: 0;
    }
  }
}
</style>
