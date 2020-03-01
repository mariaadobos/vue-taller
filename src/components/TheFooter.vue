<template>
    <footer>
    <button @click="handleGoToHome">
      <i class="fas fa-home"></i>
    </button>
    <div class="footer-upload">
      <input
        type="file"
        name="file"
        id="file"
        class="inputfile"
        :disabled="step !== 1"
        @change="handleUploadImage"
      />
      <label for="file">
        <i class="fas fa-camera-retro"></i>
      </label>
    </div>
  </footer>
  </template>

  <script>
  export default {
    name: 'MyFooter',
    props: {
    step: {
      type: Number,
      default: 1
    }
  },
    methods: {
    handleGoToHome () {
      this.$emit('go-to-home')
    },
    handleUploadImage (ev) {
      this.$emit('upload-image', ev)
    }
  }
  }
  </script>

  <style scoped lang="scss">
footer {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  height: 50px;
  background-color: #041e30;
  color: #ffffff;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
  z-index: 10;

  .fa-home{
    color: black;
  }
  .fa-camera-retro{
    font-size: 24px;
    margin-bottom: 20px;
  }
  .footer-upload {
    width: 10%;

    p {
      font-size: 0.63rem;
      position: absolute;
      left: -25px;
      top: 5px;
    }
  }

  input[name="file"] {
    visibility: hidden;
  }

  label {
    cursor: pointer;
    z-index: 99;
  }

  button {
    color: #ffffff;
  }
}
</style>