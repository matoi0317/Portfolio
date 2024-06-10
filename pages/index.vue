<template>
  <div class="profile-container">
    <!-- <header class="header">
      <GlobalHeader />
    </header> -->
    <div class="header">
        <div class="buttons">
            <button @click="$router.push('/')" class="button is-primary is-outlined is-rounded">HOME</button>
            <button @click="$router.push('/works')" class="button is-primary is-outlined is-rounded">WORKS</button>
        </div>
    </div>
    <div class="main-container">
      <div class="container-title">
        <h1 class="name">MATOI SHIBANUMA</h1>
        <div class="about">about</div>
        <p>茨城県つくば市在住の女子大生(19)。小学生の頃からプログラミングに触れ現在はフロント周りを中心に制作。茨城県立並木中等教育学校卒業。津田塾大学総合政策学部総合政策学科所属。</p>
        <div class="details">
          <div class="container">
            <h1 class="detail-title">Frontend</h1>
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
            <li>Vue.js</li>
          </div>
          <div class="container">
            <h1 class="detail-title">Python</h1>
            <li>Image Processing</li>
            <li>Image Analysis</li>
            <li>Voice Recognition</li>
          </div>
        </div>
      </div>
      <div class="container-image"></div>
    </div>
  </div>
</template>

<script>
// import GlobalHeader from "../components/GlobalHeader.vue";

export default {
};
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Archivo+Black&display=swap');
.profile-container {

  .header {
    width: 100%;
    height: 20%;
    display: flex;
    justify-content: flex-end;  
    background-color: #221F1F;
    .buttons {
        width: 50%;
        margin: 20px;
        display: flex;
        justify-content: flex-end;
        button {
            // margin: 20px;
            margin: 0 20px 0 0;
        }
    }
  }
}

.header {
  width: 100%;
}

.main-container {
  width: 100%;
  height: 100vh;
  background-color: #221F1F;
  display: flex;
  padding: 50px;
  .container-image {
    width: 30%;
    height: 80%;
    background-color: red;
    border-radius: 50px;
    background-image: url("../static/me2.JPG");
    background-position: center;
    background-size: cover;
    margin-right: 40px;
  }
  .container-title {
    width: 70%;
    height: 80%;
    .name {
      font-weight: bold;
      color: #A6BBCC;
      font-size: 64px;
      font-family: "Archivo Black", sans-serif;
      margin: 0 0 0 40px;
    }
    p {
      color: whitesmoke;
      width: 80%;
      text-indent: 1em;
      margin: 0 0 20px 40px;

    }
    .about {
      width: 100%;
      margin: 30px 40px 20px 40px;
      font-size: 36px;
      color: #A6BBCC;
      font-family: "Archivo Black", sans-serif;
      position: relative;
      &::after {
        content: "";
        display: block;
        width: 80%; /* 修正箇所 */
        height: 2px;
        background-color: #A6BBCC;
        position: absolute;
        bottom: 0; /* 修正箇所 */
        left: 0;
        transform: translateY(50%); /* 修正箇所 */
      }
    }
    .details {
      width: 100%;
      margin: 0 40px;
      display: flex;
      .container {
        width: 90%;
        li {
          padding: 10px 0;
          color: #A6BBCC;
        }
        .detail-title {
          color: #A6BBCC;
          font-family: "Archivo Black", sans-serif;
          font-size: 18px;
        }
      }
    }
  }
}
</style>
