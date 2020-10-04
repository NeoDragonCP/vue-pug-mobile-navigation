<template lang="pug">
  #content
    .teaser
      .teaser-content
        | Read Article
        i.fas.fa-chevron-right
    .infobox
      .title Articles
      .value 128
    .infobox
      .title Readers
      .value 18k
    .infobox
      .title Likes
      .value 302k
    .infobox
      .title Comments
      .value 145k
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.teaser {
  position: relative;
  width: 100%;
  max-width: 768px;
  height: 400px;
  margin-bottom: 40px;
  background-image: url("../assets/takeabreak.jpg");
  background-size: cover;
  background-position: top;
  border-radius: 20px;
  overflow: hidden;
  .teaser-content {
    position: absolute;
    left: 20px;
    bottom: 20px;
    width: 210px;
    height: 50px;
    padding: 0 0 0 20px;
    background-color: #111;
    color: #efefef;
    border-radius: 20px;
    font-size: 2rem;
    cursor: pointer;
  }
  i {
    margin-left: 0.5rem;
    font-size: 1.6rem;
  }
}
.infobox {
  float: left;
  width: 80px;
  height: 80px;
  padding: 10px;
  margin: 0 20px 20px 0;
  border-radius: 20px;
  border: 1px solid #ccc;
  .title {
    font-weight: bold;
  }
  .value {
    padding: 10px 0 0 0;
    font-size: 2rem;
  }
}
</style>
