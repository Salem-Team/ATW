<template>
  <div class="All_Comments">
    <div class="container flex">
      <div class="text">
        <div>
          “Moddy Character NFT “ The image is a high-quality digital painting
          with a resolution of 3000x2000 pixels and is optimized for the web.
          <br />
          $101,593
        </div>
        <font-awesome-icon :icon="['fas', 'angle-right']" />
      </div>
      <div class="img">
        <img src="../assets/comment_img.jpg" alt="" />
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.All_Comments {
  background: black;
  border-bottom: 40px solid hsl(272, 19%, 50%);
  .container {
    padding: 75px 0;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
    .text {
      display: flex;
      align-items: start;
      justify-content: center;
      flex-direction: column;
      gap: 20px;
      font-size: 30px;
      padding-right: 134px;
      font-weight: bold;
      color: #fff;
      svg {
        border: 2px solid var(--main-color);
        width: 40px;
        height: 40px;
        padding: 9px;
        border-radius: 50%;
        color: var(--main-color);
        cursor: pointer;
        transition: 0.3s;
        &:hover {
          filter: saturate(1.5);
        }
      }
    }
    .img img {
      width: 1260px;
      border-top-right-radius: 32px;
      border-bottom-left-radius: 32px;
      border-width: 3px;
    }
  }
}
@media (max-width: 720px) {
  .All_Comments {
    .container {
      flex-direction: column;
      gap: 20px;
      .text {
        padding: 0;
      }
    }
  }
}
</style>
