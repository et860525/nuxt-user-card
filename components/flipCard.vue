<script setup lang="ts">
interface IFlipCard {
  height: number;
}

const props = defineProps<IFlipCard>();

/* Flip card state */
const isFlipped = ref(false);

const flipCard = () => {
  isFlipped.value = !isFlipped.value;
};
</script>
<template>
  <div class="flip-card">
    <div :class="{ flipped: isFlipped }" class="flip-card-inner">
      <div class="flip-card-front">
        <div @click="flipCard()">
          <slot name="front"></slot>
        </div>
      </div>
      <div class="flip-card-back">
        <div @click="flipCard()">
          <slot name="back"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.flip-card {
  perspective: 1500px;
}
.flip-card-inner {
  position: relative;
  transform-style: preserve-3d;
  transition: transform 1s;
  transition-timing-function: ease-in-out;
  width: 100%;
  height: 400px;
}
.flip-card-inner.flipped {
  transform: rotateY(180deg);
  transition: ease-in-out 1s;
}
.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  cursor: pointer;
  -webkit-backface-visibility: hidden; /* Safari */
  backface-visibility: hidden;
}

.flip-card-back {
  transform: rotateY(180deg);
}
</style>
