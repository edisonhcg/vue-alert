<template>
  <div class="alert-wrapper" :class="positionClass" transition="fadeIn">
    <div class="alertBox">{{message}}
    </div>
  </div>
</template>

<style scope>
  .alert-wrapper {
    position: absolute;
    top: 50%;
    left: 0;
    text-align: center;
    width: 100%;
    transform: translate(0, -50%);
    transition: opacity .3s linear;
    z-index: 99999;
  }
  .alert-wrapper.alert-bottom {
    bottom: 10%;
    top: auto;
    transform: translate(0, 0);
  }
  .alert-wrapper.alert-top {
    top: 10%;
    bottom: auto;
    transform: translate(0, 0);
  }
  .alertBox {
    padding: 15px 20px;
    display: inline-block;
    background-color: rgba(0,0,0,0.75);
    border-radius: 3px;
    font-size: 0.9em;
    color: #fff;
    max-width: 80%;
    -webkit-user-select: none;
  }
  .fadeIn-transition {
    opacity: 1;
  }
  .fadeIn-leave,
  .fadeIn-enter {
    opacity: 0;
  }
</style>

<script type="text/ecmascript-6" lang="babel">
  export default {
    computed: {
      positionClass() {
        return this.position ? `alert-${this.position}` : '';
      }
    }
  };
</script>
