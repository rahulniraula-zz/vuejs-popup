<template>
  <div style="position:relative">
    <span class="fa btn btn-xs" :class="icon" @click="toggleDiv"></span>
    <div
      v-if="show"
      style="width:500px;position: absolute;top:-28px;left:20px;z-index: 444;background-color: #eee;border: 1px solid black;"
    >
      <div>
        <div class="col-md-10">
          <slot name="heading"></slot>
        </div>
        <div class="col-md-2">
          <span class="fa fa-times btn btn-danger pull-right" @click="closeDiv"></span>
        </div>
      </div>
      <slot></slot>
      <div
        style="position: absolute;
                    background-color: #eee;
                    width: 15px;
                    height: 15px;
                    top: 28px;
                    z-index: -1;
                    left: -9px;
                    transform: rotate(42deg);
                    border-bottom: 1px solid black;
                    border-left: 1px solid black;"
      ></div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["icon"],
  data: function() {
    return {
      show: false
    };
  },
  methods: {
    toggleDiv: function() {
      return (this.show = !this.show);
    },
    closeDiv() {
      return (this.show = false);
    }
  }
};
</script>
