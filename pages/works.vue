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
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
            <p class="modal-card-title">うんち出たよと教え隊！</p>
            <button class="delete" aria-label="close"></button>
            </header>
            <section class="modal-card-body">
                <h1>概要</h1>
                <p>犬がトイレをしたかどうか確認するのが面倒だったため、画像認識技術を利用し、犬のトイレを検知するシステムを開発。犬がトイレをした後にはLINEに通知が来るようにした。</p><br>
                <h1>開発</h1>
                <li>Python</li>
                <li>RaspberryPi</li>
                <li>LINE Notify</li>
                <br>
                <h1>受賞歴</h1>
                <li>第62回日本学生科学賞入選2等</li>
            </section>
            <footer class="modal-card-foot">
            <div class="buttons">
                <button class="button is-success is-outlined is-rounded">Save changes</button>
                <button class="button is-rounded">Cancel</button>
            </div>
            </footer>
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
    .modal-card {
        .delete {
            margin-right: 20px;
        }
        .modal-card-body {
            padding: 20px;
            h1 {
                font-weight: bold;
                font-size: 24px;
            }
            p {
                text-indent: 1em;
                padding: 10px 0;
            }
            li {
                padding: 5px 0;
            }
        }
        .modal-card-title {
            padding: 30px 20px;
            font-weight: bold;
        }
        .buttons {
            display: flex;
            justify-content: flex-end;
            button {
            padding: 10px;
            margin: 10px;
        }
        }
    }
  }


  </style>
  