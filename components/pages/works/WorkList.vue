<template>
  <div class="list-container">
    <!-- BlockBits -->
    <div class="container">
      <div class="tags">
        <span class="tag python">Python</span>
        <span class="tag javascript">Javascript</span>
        <span class="tag html">HTML/CSS</span>
      </div>
      <div>
        <div class="contents blockbits">
          <div class="icon blockbits"></div>
          <div class="details">
            <h1>Java学習サイトのフロント制作</h1>
            <p>Block Bitsは実際に手を動かしながら、プログラミングのスキルを楽しく学べるプログラミング学習サービスです。MinecraftのMOD制作を通じてコンピュータサイエンスやJavaプログラミングのスキルを楽しく学びましょう！</p>
          </div>
        </div>
        <div class="buttons">
          <a href="https://block-bits.com/"><button class="button is-dark">サイト</button></a>
          <button class="button is-dark">GitHub</button>
        </div>
      </div>
    </div>
    <!-- サマーインターン -->
    <div class="container">
      <div class="tags">
        <span class="tag other">その他</span>
      </div>
      <div>
        <div class="contents intern">
          <div class="icon intern"></div>
          <div class="details">
            <h1>富士通サマーインターン</h1>
            <p>7/8~7/12に開催されたFujitsu Job Experience Internshipに参加しました。ESとBPの職業体験を5日間にかけて行うワークショップ型のインターンです。初のインターン参加ということでハードでしたが楽しかった5日間でした。</p>
          </div>
        </div>
      </div>
    </div>
    <!-- オンライン学習サイト -->
    <div class="container">
      <div class="tags">
        <span class="tag python">Python</span>
        <span class="tag javascript">Javascript</span>
        <span class="tag html">HTML/CSS</span>
      </div>
      <div>
        <div class="contents study">
          <div class="icon study"></div>
          <div class="details">
            <h1>オンライン学習サイト</h1>
            <p>Block Bitsは実際に手を動かしながら、プログラミングのスキルを楽しく学べるプログラミング学習サービスです。MinecraftのMOD制作を通じてコンピュータサイエンスやJavaプログラミングのスキルを楽しく学びましょう！</p>
          </div>
        </div>
        <div class="buttons">
          <a href="https://studybu.com/"><button class="button is-dark">サイト</button></a>
        </div>
      </div>
    </div>
    <!-- zudada -->
    <div class="container">
      <div class="tags">
        <span class="tag javascript">Javascript</span>
        <span class="tag html">HTML/CSS</span>
      </div>
      <div>
        <div class="contents zudada">
          <div class="icon zudada"></div>
          <div class="details">
            <h1>タイピングサイトのLP制作</h1>
            <p>無料タイピングサイト「ずだだ」のLPを制作しました。かなりユニークな妖怪のイラストをメインキャラクターとしているため、デザインをキャラクターに合わせるのが大変でした。今後はフロント開発にも携わっていく予定です。</p>
          </div>
        </div>
        <div class="buttons">
          <a href="https://app.zudada.me/"><button class="button is-dark">サイト</button></a>
        </div>
      </div>
    </div>
    <!-- 顔認証 -->
    <div class="container">
      <div class="tags">
        <span class="tag python">Python</span>
        <span class="tag javascript">Javascript</span>
        <span class="tag html">HTML/CSS</span>
      </div>
      <div>
        <div class="contents face">
          <div class="icon face"></div>
          <div class="details">
            <h1>顔認証システムの開発</h1>
            <p>OpenCV×Pythonで画像処理システムを作成し、プログラミングスクールの顔認証入退室管理システムを制作しました。子供達が楽しく使ってくれるようにSnowのようなフィルター機能も搭載しています。</p>
          </div>
        </div>
        <div class="buttons">
          <a href="https://github.com/matoi0317/opencv"><button class="button is-dark">GitHub</button></a>
        </div>
      </div>
    </div>
    <div class="container" style="opacity:0 ;"></div>
  </div>
</template>


<script setup lang="ts"></script>

<style scoped lang="scss">
.list-container {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  padding: 20px;
  .container {
    position: relative;  // 追加
    margin: 40px;
    width: 400px;
    height: 360px;
    background-color: #1F2124;
    padding: 40px;
    border-radius: 20px;
    .buttons {
      margin-top: 20px;
      display: flex;
    }
    .tags {
      .tag {
        padding: 15px 20px;
        border-radius: 20px;
        font-weight: 500;
        &.python {
          background-color: #212B36;
          color: #35A6FF;
        }
        &.java {
          background-color: #312C21;
          color: #FFAA01;
        }
        &.javascript {
          background-color: #242D28;
          color: #56B158;
        }
        &.html {
          background-color: #2F2629;
          color: #FE6E6D;
        }
        &.other {
          background-color: #2C2F33;
          color: #B3B6B9;
        }
      }
    }
    .contents {
      width: 100%;
      height: 100%;
      display: flex;
      .details {
        margin-left: 20px;
        h1 {
          font-size: 24px;
          color: #cccccc;
          font-weight: bold;
        }
        p {
          text-indent: 1em;
          color: #757A86;
        }
      }
      .icon {
        width: 150px;
        height: 150px;
        // border-radius: 50%;
        background-position: center;
        background-size: contain;
        background-repeat: no-repeat;
        background-size: 200px auto;
        &.blockbits {
          background-image: url("~/static/b2/b2.png");
        }
        &.intern {
          background-image: url("~/static/intern/huzitu.png")
        }
        &.study {
          background-image: url("~/static/studybu/logo.png")
        }
        &.zudada {
          background-image: url("~/static/zudada/zudada.png")
        }
        &.face {
          background-image: url("~/static/face/face2.png")
        }
      }
    }
    &.prepare {
      .overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, 0.7);  // 黒っぽい膜
        border-radius: 20px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
        font-size: 24px;
        font-weight: bold;
      }
    }
  }
}

.list-container:after {
    display: block;
    width: 400px;
    height: 0;
}
</style>
