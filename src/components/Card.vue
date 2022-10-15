<template>
  <div class="card">
    <div class="card__inner" :class="{'isFlipped': isFlipped}" @click="onToggleFlipCard">
      <div class="card__face card__face--front">
        <div class="card__content">front</div>
      </div>
      <div class="card__face card__face--back">
        <div class="card__content">back</div>
      </div>
    </div>

  </div>
</template>
<script>
export default {

  data() {
    return {
      isFlipped: false,
    };
  },
  methods: {
    onToggleFlipCard() {
      this.isFlipped = !this.isFlipped
    }
  }
}



</script>
<style lang="css" scoped>
.card {
  display: inline-block;
  margin-right: 1rem;
  margin-bottom: 1rem;
  height: 120px;
  width: 90px;
}

.card__inner {
  width: 100%;
  height: 100%;
  transition: transform 1s;
  transform-style: preserve-3d;
  cursor: pointer;
  position: relative;
}

.card__inner.isFlipped {
  transform: rotateY(-180deg);
}

.card__face {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  overflow: hidden;
  border-radius: 1rem;
  padding: 1rem;
  box-shadow: 0px 3px 10px 3px lightslategray;
}
.card__face--back {
  background-color: var(--light);
  transform: rotateY(-180deg);
}
</style>