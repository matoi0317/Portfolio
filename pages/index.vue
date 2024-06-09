<template>
  <div class="profile-container">
    <header class="header">
      <GlobalHeader />
    </header>
    <div class="main-content">
      <div class="image-section">
        <img src="../static/me2.JPG" alt="Profile Image" class="profile-image">
        <div class="info-section">
          <h1>Matoi Shibanuma</h1>
          <p>(she/her)</p>
          <p>Web Design</p>
        </div>
      </div>
      <div class="about-section">
        <h2>About Me</h2>
        <hr />
        <p>茨城県つくば市在住の女子大生です。茨城県立並木中等教育学校卒業、現在は津田塾大学総合政策学部総合政策学科に所属しています。Web制作、フロントエンド開発が好きです。使える言語はPython・Javascriptです。</p>
        <div class="social-icons">
          <i class="fab fa-instagram"></i>
          <i class="fab fa-twitter"></i>
          <i class="fab fa-facebook"></i>
          <i class="fab fa-linkedin"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GlobalHeader from "../components/GlobalHeader.vue";

export default {
  components: {
    GlobalHeader
  }
};
</script>

<style scoped>
.profile-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: Arial, sans-serif;
}

.header {
  width: 100%;
}

.main-content {
  display: flex;
  width: 100%;
  margin-top: 50px;
}

.image-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 50%;
}

.profile-image {
  width: 80%;
  /* border-radius: 50%; */
}

.info-section {
  text-align: center;
  margin-top: 20px;
}

.info-section h1 {
  margin: 0;
}

.info-section p {
  margin: 5px 0;
}

.email-button {
  margin-top: 10px;
  padding: 10px 20px;
  background-color: black;
  color: white;
  border: none;
  cursor: pointer;
}

.about-section {
  background-color: #e0f0ff;
  padding: 20px;
  width: 50%;
  margin-left: 20px;
  margin-right: 80px;
  border-radius: 10px;
}

.about-section h2 {
  margin-top: 0;
}

.about-section hr {
  margin: 10px 0;
}

.button-section {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
}

.resume-button, .portfolio-button {
  padding: 10px 20px;
  background-color: white;
  border: 1px solid #000;
  cursor: pointer;
}

.social-icons {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.social-icons i {
  font-size: 24px;
  margin: 0 10px;
  cursor: pointer;
}
</style>
