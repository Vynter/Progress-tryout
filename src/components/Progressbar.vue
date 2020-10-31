<template>
  <div class="pb">
    <div class="progress">
      <div
        class="progress-bar bg-dark"
        role="progressbar"
        :style="{ width: count + 2 + `%` }"
        :aria-valuenow="count"
        aria-valuemin="0"
        aria-valuemax="100"
      >
        {{ count }}%
      </div>
    </div>
    <button
      v-if="on == true"
      type="button"
      class="btn btn-outline-dark mt-3 p-2"
      @click="start"
    >
      Démarrer
    </button>
    <button
      v-else
      type="button"
      class="btn btn-outline-dark mt-3 p-2"
      @click="stoped"
    >
      Pause
    </button>
    <div>
      <button
        v-if="on == true"
        type="button"
        class="btn btn-outline-danger mt-3 p-2"
        @click="reset"
      >
        reset
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "progress-bar",
  data() {
    return {
      on: true,
      count: 25,
    };
  },
  methods: {
    start() {
      if (this.count < 100) {
        this.on = false;
        this.interval = setInterval(() => {
          if (this.count >= 100) {
            clearInterval();
          } else {
            this.count++;
          }
        }, 100);
      }
    },
    stoped() {
      this.on = true;
      clearInterval(this.interval);
    },
    reset() {
      this.count = 0;
    },
  },
};
</script>

<style scoped>
.progress {
  margin: auto;
  width: 500px;
  height: 20px;
  border-radius: 20px;
}
button {
  width: 100px;
}
</style>
