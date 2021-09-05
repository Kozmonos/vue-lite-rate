<template>
  <div class="stars">
    <span v-if="rateNumber" class="rate">{{ star.toFixed(1) }}</span>
    <div v-for="n in starInt" :key="n + '_full'">
      <img svg-inline src="../static/assets/full_star.svg" />
    </div>
    <div v-if="halfStar">
      <img svg-inline src="../static/assets/half_star.svg" />
    </div>
    <div v-for="n in emptyStar" :key="n + '_empty'">
      <img svg-inline src="../static/assets/empty_star.svg" />
    </div>

    <span v-if="commentNumber">({{ commentNumber }})</span>
  </div>
</template>
<script>
export default {
  data() {
    return {
      halfStar: false,
    };
  },
  props: {
    star: {
      required: true,
    },
    rateNumber: {
      type: Boolean,
    },
    commentNumber: {
      type: String,
    },
  },
  created() {
    this.star = Number(this.star);

    this.halfStar = Number.isInteger(this.star) ? false : true;
    this.starInt = parseInt(this.star);
    this.emptyStar = 5 - this.starInt - (this.halfStar ? 1 : 0);
  },
};
</script>
<style scoped>
.stars {
  display: flex;
  align-items: center;
}
.stars span {
  margin-right: 2px;
  margin-left: 2px;
}
.stars .rate {
  color: #e8a336;
  font-weight: 700;
}
div,
svg {
  width: 15px;
  height: 15px;
}
</style>