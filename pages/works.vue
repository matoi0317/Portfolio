<template>
    <div>
      <GlobalHeader />
      <div class="container">
        <img src="../static/unti.png" class="slide-in-left main-image" @click="openModal('unti')">
        <div class="side-images">
          <img src="../static/face.png" class="slide-in-left small-image" @click="openModal('face')">
          <div class="vertical-images">
            <img src="../static/syaberitai.png" class="slide-in-right small-image" style="margin-top: 50px;" @click="openModal('syaberitai')">
            <img src="../static/wakarutte.png" class="slide-in-right small-image" style="margin-top: 50px;" @click="openModal('wakarutte')">
          </div>
        </div>
      </div>
  
      <div v-if="isModalOpen" class="modal" @click="closeModal">
        <div class="modal-background"></div>
        <div class="modal-card" @click.stop>
          <header class="modal-card-head">
            <p class="modal-card-title">{{ modalContent.title }}</p>
            <button class="delete" aria-label="close" @click="closeModal"></button>
          </header>
          <section class="modal-card-body">
            <h1>概要</h1>
            <p>{{ modalContent.description }}</p><br>
            <h1>開発</h1>
            <li v-for="tech in modalContent.tech" :key="tech">{{ tech }}</li>
            <br>
            <!-- <h1>Photo</h1>
            <div class="modal-images">
              <img v-for="img in modalContent.images" :src="img" class="modal-image"><br>
            </div> -->
            <h1>受賞歴</h1>
            <li v-for="award in modalContent.awards" :key="award">{{ award }}</li>
          </section>
          <footer class="modal-card-foot">
            <div class="buttons">
              <a :href="modalContent.github" v-if="modalContent.github" target="_blank" class="button is-primary is-rounded">View on GitHub</a>

            </div>
          </footer>
        </div>
      </div>
    </div>
  </template>
  
  
  <script>
import GlobalHeader from "../components/GlobalHeader.vue";

export default {
  components: { GlobalHeader },
  data() {
    return {
      isModalOpen: false,
      modalContent: {},
      contentData: {
        unti: {
          title: 'うんち出たよと教え隊！',
          description: '犬がトイレをしたかどうか確認するのが面倒だったため、画像認識技術を利用し、犬のトイレを検知するシステムを開発。犬がトイレをした後にはLINEに通知が来るようにした。',
          tech: ['Python', 'RaspberryPi', 'LINE Notify'],
          awards: ['第62回日本学生科学賞 入選2等'],
          images: ['../static/unti/1.png', '../static/unti/2.png', '../static/unti/3.png']
        },
        face: {
          title: '顔認識システム',
          description: '画像処理技術を利⽤し顔認証による⼊室管理システムの開発を⾏なっている。従来のシステムで はバーコードやQRコードを利⽤するシステムが多いが紛失してしまった時にシステムが利⽤できな いなどまだまだ課題がある。さらに、このシステムでは⼊室時に、作成したフィルター機能によって顔にエフェクトをつけることができ、ただの顔認証システムではなく利⽤者が楽しんでもらえるような⼯夫をした。',
          tech: ['Python', 'OpenCV', 'Javascript'],
          awards: ['なし'],
          images: ['../static/face/face1.png', '../static/face/face2.png', '../static/face/face3.png', '../static/face/face4.png', '../static/face/face5.png'],
          github: 'https://github.com/matoi0317/face_recognition'
        },
        syaberitai: {
          title: 'あなたとしゃべりたい',
          description: '初めのアイデアとして、⾳声解析プログラムを作成した。祖⺟は気管⽀切開⼿術を受けており、わ ずかに漏れる「はっ」という⾳を利⽤してコミュニケーションを図るアイデアだった。しかしなが ら、環境⾳と混ざり合い、⾳声解析が難しいことが判明し、このアイデアは断念せざるを得なかっ た。次に、「まばたき」を⽤いてコミュニケーションを試みるアイデアが浮かんだ。祖⺟は唯⼀「ま ばたき」を⾃⼒で⾏える動作であり、⺟が以前から「テレビを⾒たいと思ったら⽬を閉じてみて」と いうような会話を祖⺟としていたことからアイデアを得た。画像解析プログラムを開発し、まばたき の回数に応じてコミュニケーションを取るアプリの開発を進めた。',
          tech: ['Python', 'Javascript', 'Vue.js'],
          awards: ['IBARAKIドリームパスアワード 最優秀賞', '第63回日本学生科学賞入選3等', '一般社団法人情報処理学会 初等中等教育委員会委員長賞'],
          images: ['../static/syaberitai/1.png', '../static/syaberitai/2.png', '../static/syaberitai/3.png'],
          github: 'https://github.com/matoi0317/eye_blink_communicator'
        },
        wakarutte: {
          title: 'わかるって',
          description: '⾼齢者などIT機器の操作に不慣れな⼈にとって、医療⽤アプリを操作することに抵抗を感じるかもしれない。そこで、⾃宅にいながら⾳声だけで体調管理ができるアプリがあれば便利なのではないかと考え開発を⾏うことにした。RaspberryPiの⾳声認識を⽤いた医療⽤カルテを作成するアプリを作成。これにより、在宅医療や通院している患者の⽇々の状況を電⼦カルテ化でき、診察時の効率化等に寄与できると考える。',
          tech: ['Python', 'Javascript', 'RaspberryPi'],
          awards: ['JoyoHighSchoolテックコンテスト 優秀賞'],
          images: ['../static/wakarutte/1.png', '../static/wakarutte/2.png', '../static/wakarutte/3.png'],
          github: 'https://github.com/matoi0317/karute'
        }
      }
    };
  },
  methods: {
    openModal(key) {
      this.modalContent = this.contentData[key];
    //   this.modalContent.images = this.modalContent.images.map(img => require(`${img}`));
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
      this.modalContent = {};
    }
  }
};
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
          padding: 30px;
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
          a.button {
            padding: 10px;
            margin: 10px;
          }
      }
  }
}
</style>
