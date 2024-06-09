<template>
    <div>
      <GlobalHeader />
      <div class="container">
        <img src="../static/unti.png" class="slide-in-left main-image" @click="openModal('../static/unti.png')">
        <div class="side-images">
          <img src="../static/face.png" class="slide-in-left small-image" @click="openModal('../static/face.png')">
          <div class="vertical-images">
            <img src="../static/syaberitai.png" class="slide-in-right small-image" style="margin-top: 50px;" @click="openModal('../static/syaberitai.png')">
            <img src="../static/wakarutte.png" class="slide-in-right small-image" style="margin-top: 50px;" @click="openModal('../static/wakarutte.png')">
          </div>
        </div>
      </div>
      <div v-if="isModalOpen" class="modal" @click="closeModal">
        <div class="modal-content" @click.stop>
          <span class="close-button" @click="closeModal">&times;</span>
          <img :src="modalImage" class="modal-image">
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import GlobalHeader from "../components/GlobalHeader.vue"
  
  export default {
    components: { GlobalHeader },
    data() {
      return {
        isModalOpen: false,
        modalImage: ''
      }
    },
    methods: {
      openModal(image) {
        this.modalImage = image;
        this.isModalOpen = true;
      },
      closeModal() {
        this.isModalOpen = false;
        this.modalImage = '';
      }
    }
  }
  </script>
  
  <style scoped lang="scss">
  * {
    padding: 0;
    margin: 0;
  }
  
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 50px;
    width: 70%;
    margin: 0 auto;
  
    .main-image {
      width: 100%;
      animation: slide-in-left 1s ease-out;
      cursor: pointer;
    }
  
    .side-images {
      display: flex;
      margin-top: 20px;
      padding-bottom: 200px;
  
      .vertical-images {
        display: flex;
        flex-direction: column;
        margin-left: 20px;
  
        .small-image {
          width: 100%;
          animation: slide-in-right 1s ease-out;
          cursor: pointer;
        }
      }
  
      .small-image {
        width: 40%;
        animation: slide-in-left 1s ease-out;
        cursor: pointer;
      }
    }
  }
  
  /* スライドインアニメーションの定義 */
  @keyframes slide-in-left {
    0% {
      transform: translateX(-100%);
      opacity: 0;
    }
    100% {
      transform: translateX(0);
      opacity: 1;
    }
  }
  
  /* スライドインアニメーションの定義 */
  @keyframes slide-in-right {
    0% {
      transform: translateX(100%);
      opacity: 0;
    }
    100% {
      transform: translateX(0);
      opacity: 1;
    }
  }
  
  /* モーダルウィンドウのスタイル */
  .modal {
    display: flex;
    justify-content: center;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.8);
  }
  
  .modal-content {
    position: relative;
    background-color: #fff;
    padding: 20px;
    border-radius: 10px;
    max-width: 80%;
    max-height: 80%;
    overflow: auto;
  }
  
  .close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 30px;
    cursor: pointer;
  }
  
  .modal-image {
    width: 100%;
    height: auto;
  }
  </style>
  