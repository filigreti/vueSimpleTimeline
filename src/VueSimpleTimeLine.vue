<template>
  <main>
    <div class="main-timeline">
      <div v-for="(time,index) in newTimeLine" :key="index">
        <div class="timeline-container">
          <div :class="`time${index}`" class="time">
            <div class="timer">{{time.date}}</div>
            <div :style="`background:${time.iconDotsColor}`" class="iconDot"></div>
          </div>
          <div class="kred">
            <div class="history" v-for="(dats,index) in time.history" :key="index">
              <div class="history-body">
                <div class="data-name">{{dats.name}}</div>
                <div class="data-summary">{{dats.summary}}</div>
                <div class="data-time">{{dats.time}}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  props: {
    Timeline: {
      type: Array,
      required: true
    },
    TimelineColor: {
      type: String,
      default: "#D4D9DD"
    }
  },
  watch: {
    TimelineColor: {
      immediate: true,
      handler(x) {
        if (x) {
          document.documentElement.style.setProperty(
            "--selection-background",
            x
          );
        }
      }
    }
  },
  computed: {
    newTimeLine() {
      return this.Timeline;
    }
  },
  mounted() {
    let k = this.Timeline.length - 1;
    let style = document.styleSheets.length - 1;
    console.log(style);
    document.styleSheets[style].addRule(`.time${k}::after`, "content: none");
    document.styleSheets[style].insertRule(
      `.time${k}::after { color: green }`,
      0
    );
  }
};
</script>

<style>
:root {
  --selection-background: black;
}
.timeline-container {
  display: flex;
}
.iconDot {
  position: absolute;
  right: -24.5px;
  width: 10px;
  height: 10px;
  z-index: 5;
  border-radius: 50%;
}

.history {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 37px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.history-body {
  border: 1px solid #d4d9dd;
  margin-bottom: 1rem;
  padding: 0.5rem;
}

.time {
  position: relative;
  display: flex;
}
.time::after {
  content: "";
  position: absolute;
  width: 1px;
  background: var(--selection-background);
  height: 100%;
  right: -20px;
}

.area {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.kred {
  margin-left: 3rem;
  position: relative;
  width: 100%;
  height: 100%;
}

.timer {
  margin-top: -4px !important;
}
</style>