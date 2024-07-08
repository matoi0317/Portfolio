<template>
  <div>
    <GlobalHeader />
    <div class="portfolio-container">
      <div v-for="item in sortedPortfolioItems" :key="item.id" class="portfolio-item">
        <img :src="item.thumbnail" class="portfolio-thumbnail" />
        <div class="portfolio-details">
          <h2 class="portfolio-title">{{ item.title }}</h2>
          <p class="portfolio-date">{{ item.date }}</p>
          <p class="portfolio-description">{{ item.overview }}</p>
          <button @click="openModal(item)">詳しく見る</button>
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
      portfolioItems: [
        {
          id: 1,
          title: 'うんち出たよと教え隊！',
          date: '2018-06-01',
          overview: '画像処理技術を用いたトイレ確認アプリの作成',
          description: '犬がトイレをしたかどうか確認するのが面倒だったため、画像認識技術を利用し、犬のトイレを検知するシステムを開発。犬がトイレをした後にはLINEに通知が来るようにした。',
          tech: ['Python', 'RaspberryPi', 'LINE Notify'],
          awards: ['第62回日本学生科学賞 入選2等'],
          thumbnail: 'unti/unti.png',
          github: ''
        },
        {
          id: 2,
          title: '顔認識システム',
          date: '2023-12-15',
          overview: 'Python × OpenCVを用いた顔認証システムの作成。フィルター機能の搭載。',
          description: '画像処理技術を利用し顔認証による入室管理システムの開発を行なっている。従来のシステムではバーコードやQRコードを利用するシステムが多いが紛失してしまった時にシステムが利用できないなどまだまだ課題がある。さらに、このシステムでは入室時に、作成したフィルター機能によって顔にエフェクトをつけることができ、ただの顔認証システムではなく利用者が楽しんでもらえるような工夫をした。',
          tech: ['Python', 'OpenCV', 'Javascript'],
          awards: ['なし'],
          thumbnail: 'face/face1.png',
          github: 'https://github.com/matoi0317/face_recognition'
        },
        {
          id: 3,
          title: 'あなたとしゃべりたい',
          date: '2022-08-30',
          overview: '音声認識技術を応用したコミュニケーションアプリの作成。LINEとの連携。',
          description: '初めのアイデアとして、音声解析プログラムを作成した。祖母は気管支切開手術を受けており、わずかに漏れる「はっ」という音を利用してコミュニケーションを図るアイデアだった。しかしながら、環境音と混ざり合い、音声解析が難しいことが判明し、このアイデアは断念せざるを得なかった。次に、「まばたき」を用いてコミュニケーションを試みるアイデアが浮かんだ。祖母は唯一「まばたき」を自力で行える動作であり、母が以前から「テレビを見たいと思ったら目を閉じてみて」というような会話を祖母としていたことからアイデアを得た。画像解析プログラムを開発し、まばたきの回数に応じてコミュニケーションを取るアプリの開発を進めた。',
          tech: ['Python', 'Javascript', 'Vue.js'],
          awards: ['IBARAKIドリームパスアワード 最優秀賞', '第63回日本学生科学賞入選3等', '一般社団法人情報処理学会 初等中等教育委員会委員長賞'],
          thumbnail: 'syaberitai/syaberitai.png',
          github: 'https://github.com/matoi0317/eye_blink_communicator'
        },
        {
          id: 4,
          title: 'わかるって',
          date: '2021-05-10',
          overview: '音声認識技術を応用した体調管理アプリの作成',
          description: '高齢者などIT機器の操作に不慣れな人にとって、医療用アプリを操作することに抵抗を感じるかもしれない。そこで、自宅にいながら音声だけで体調管理ができるアプリがあれば便利なのではないかと考え開発を行うことにした。RaspberryPiの音声認識を用いた医療用カルテを作成するアプリを作成。これにより、在宅医療や通院している患者の日々の状況を電子カルテ化でき、診察時の効率化等に寄与できると考える。',
          tech: ['Python', 'Javascript', 'RaspberryPi'],
          awards: ['JoyoHighSchoolテックコンテスト 優秀賞'],
          thumbnail: 'wakarutte/wakarutte.png',
          github: 'https://github.com/matoi0317/karute'
        },
        {
          id: 5,
          title: 'タイピングゲームのLP制作',
          date: '2024-06-01',
          overview: 'ユニークなイラストを用いたタイピングサイトのLP制作',
          description: '高齢者などIT機器の操作に不慣れな人にとって、医療用アプリを操作することに抵抗を感じるかもしれない。そこで、自宅にいながら音声だけで体調管理ができるアプリがあれば便利なのではないかと考え開発を行うことにした。RaspberryPiの音声認識を用いた医療用カルテを作成するアプリを作成。これにより、在宅医療や通院している患者の日々の状況を電子カルテ化でき、診察時の効率化等に寄与できると考える。',
          tech: ['Javascript', 'JTML', 'CSS'],
          thumbnail: 'zudada/zudada.png',
          github: 'https://github.com/matoi0317/karute'
        },
        {
          id: 6,
          title: '予備校の動画学習サイト制作',
          date: '2024-05-01',
          overview: 'エルステップを用いた生徒の管理、動画閲覧サイトの制作',
          description: '高齢者などIT機器の操作に不慣れな人にとって、医療用アプリを操作することに抵抗を感じるかもしれない。そこで、自宅にいながら音声だけで体調管理ができるアプリがあれば便利なのではないかと考え開発を行うことにした。RaspberryPiの音声認識を用いた医療用カルテを作成するアプリを作成。これにより、在宅医療や通院している患者の日々の状況を電子カルテ化でき、診察時の効率化等に寄与できると考える。',
          tech: ['Javascript', 'RaspberryPi'],
          thumbnail: 'studybu/studybu.jpg',
          github: 'https://github.com/matoi0317/karute'
        },
        // {
        //   id: 7,
        //   title: '富士通サマーインターン',
        //   date: '2024-07-08',
        //   overview: '富士通サマーインターン参加記録',
        //   description: '今後追加予定',
        //   thumbnail: '../static/zudada/zudada1.png',
        // }
      ]
    };
  },
  computed: {
    sortedPortfolioItems() {
      return this.portfolioItems.sort((a, b) => new Date(b.date) - new Date(a.date));
    }
  },
  methods: {
    openModal(item) {
      this.modalContent = item;
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
      this.modalContent = {};
    }
  }
};
</script>

<style scoped>
.portfolio-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  padding: 20px;
}

.portfolio-item {
  width: 30%;
  margin: 20px;
  border: 1px solid #ddd;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
}

.portfolio-item:hover {
  transform: scale(1.05);
}

.portfolio-thumbnail {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.portfolio-details {
  padding: 20px;
}

.portfolio-title {
  font-size: 1.5em;
  margin-bottom: 10px;
}

.portfolio-date {
  color: #888;
  margin-bottom: 10px;
}

.portfolio-description {
  margin-bottom: 20px;
}

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

.modal-card {
  width: 60%;
  background-color: white;
  border-radius: 10px;
  overflow: hidden;
}

.modal-card-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  border-bottom: 1px solid #ddd;
}

.modal-card-title {
  font-size: 1.5em;
}

.modal-card-body {
  padding: 20px;
}

.modal-card-foot {
  display: flex;
  justify-content: flex-end;
  padding: 20px;
  border-top: 1px solid #ddd;
}
</style>
