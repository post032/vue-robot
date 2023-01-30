<template>
  <div>
    <div class="top-row">
      <div class="top part">
        <img v-bind:src="availableParts.heads[selectedHeadIndex].src" title="head"/>
        <button v-on:click="selectPrevHead()" class="prev-selector">&#9668;</button>
        <button v-on:click="selectNextHead()" class="next-selector">&#9658;</button>
      </div>
    </div>
    <div class="middle-row">
      <div class="left part">
        <img v-bind:src="availableParts.arms[selectedLeftArmsIndex].src" title="left arm"/>
        <button v-on:click="selectPrevLeftArm()" class="prev-selector">&#9650;</button>
        <button v-on:click="selectNextLeftArm()" class="next-selector">&#9660;</button>
      </div>
      <div class="center part">
        <img v-bind:src="availableParts.torsos[selectedTorosIndex].src" title="left arm"/>
        <button v-on:click="selectPrevTors()" class="prev-selector">&#9668;</button>
        <button v-on:click="selectNextTors()" class="next-selector">&#9658;</button>
      </div>
      <div class="right part">
        <img v-bind:src="availableParts.arms[selectedRightArmsIndex].src" title="left arm"/>
        <button v-on:click="selectPrevRightArm()" class="prev-selector">&#9650;</button>
        <button v-on:click="selectNextRightArm()" class="next-selector">&#9660;</button>
      </div>
    </div>
    <div class="bottom-row">
      <div class="bottom part">
        <img v-bind:src="availableParts.bases[selectedBaseIndex].src" title="left arm"/>
        <button v-on:click="selectPrevBase()" class="prev-selector">&#9668;</button>
        <button v-on:click="selectNextBase()" class="next-selector">&#9658;</button>
      </div>
    </div>
  </div>
</template>

<script>
import availableParts from '../data/parts';

function getPrevValidIndex(index, lenght) {
  const deprecatedIndex = index - 1;
  return deprecatedIndex < 0 ? lenght - 1 : deprecatedIndex;
}

function getNextValidIndex(index, lenght) {
  const incrementedIndex = index + 1;
  return incrementedIndex > lenght - 1 ? 0 : incrementedIndex;
}

export default {
  name: 'RobotBuilder',
  data() {
    return {
      availableParts,
      selectedHeadIndex: 0,
      selectedLeftArmsIndex: 0,
      selectedRightArmsIndex: 0,
      selectedTorosIndex: 0,
      selectedBaseIndex: 0,
    };
  },

  methods: {
    selectNextHead() {
      this.selectedHeadIndex = getNextValidIndex(
        this.selectedHeadIndex,
        this.availableParts.heads.length,
      );
    },
    selectPrevHead() {
      this.selectedHeadIndex = getPrevValidIndex(
        this.selectedHeadIndex,
        this.availableParts.heads.length,
      );
    },
    selectNextLeftArm() {
      this.selectedLeftArmsIndex = getNextValidIndex(
        this.selectedLeftArmsIndex,
        this.availableParts.arms.length,
      );
    },
    selectPrevLeftArm() {
      this.selectedLeftArmsIndex = getPrevValidIndex(
        this.selectedLeftArmsIndex,
        this.availableParts.arms.length,
      );
    },
    selectNextTors() {
      this.selectedTorosIndex = getNextValidIndex(
        this.selectedTorosIndex,
        this.availableParts.torsos.length,
      );
    },
    selectPrevTors() {
      this.selectedTorosIndex = getPrevValidIndex(
        this.selectedTorosIndex,
        this.availableParts.torsos.length,
      );
    },
    selectNextRightArm() {
      this.selectedRightArmsIndex = getNextValidIndex(
        this.selectedRightArmsIndex,
        this.availableParts.arms.length,
      );
    },
    selectPrevRightArm() {
      this.selectedRightArmsIndex = getPrevValidIndex(
        this.selectedRightArmsIndex,
        this.availableParts.arms.length,
      );
    },
    selectNextBase() {
      this.selectedBaseIndex = getNextValidIndex(
        this.selectedBaseIndex,
        this.availableParts.bases.length,
      );
    },
    selectPrevBase() {
      this.selectedBaseIndex = getPrevValidIndex(
        this.selectedBaseIndex,
        this.availableParts.bases.length,
      );
    },
  },
};
</script>

<style>
.part {
  position: relative;
  width: 165px;
  height: 165px;
  border: 3px solid #aaa;
}

.part img {
  width: 165px;
}

.top-row {
  display: flex;
  justify-content: space-around;
}

.middle-row {
  display: flex;
  justify-content: center;
}

.bottom-row {
  display: flex;
  justify-content: space-around;
  border-top: none;
}

.head {
  border-bottom: none;
}

.left {
  border-right: none;
}

.right {
  border-left: none;
}

.left img {
  transform: rotate(-90deg);
}

.right img {
  transform: rotate(90deg);
}

.bottom {
  border-top: none;
}

.prev-selector {
  position: absolute;
  z-index: 1;
  top: -3px;
  left: -28px;
  width: 25px;
  height: 171px;
}

.next-selector {
  position: absolute;
  z-index: 1;
  top: -3px;
  right: -28px;
  width: 25px;
  height: 171px;
}

.center .prev-selector, .center .next-selector {
  opacity: 0.8;
}

.left .prev-selector {
  top: -28px;
  left: -3px;
  width: 144px;
  height: 25px;
}

.left .next-selector {
  top: auto;
  bottom: -28px;
  left: -3px;
  width: 144px;
  height: 25px;
}

.right .prev-selector {
  top: -28px;
  left: 24px;
  width: 144px;
  height: 25px;
}

.right .next-selector {
  top: auto;
  bottom: -28px;
  left: 24px;
  width: 144px;
  height: 25px;
}

.right .next-selector {
  right: -3px;
}

</style>