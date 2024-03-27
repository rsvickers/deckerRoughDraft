<template>
  <div>
    <div class="container-fluid">
      <section class="row">
        <div class="col-12">
          <h1 class="d-flex justify-content-center grayBg mt-3">Challenges</h1>
        </div>
      </section>
    </div>

    <div class="container-fluid">
      <section class="row mx-5 mt-2 d-flex justify-content-between">
        <div class="col-5 text-center grayBg2">
          <h1>Recommended. I need to find a project for me.</h1>
        </div>
        <div class="col-5 mx-5 text-center grayBg2">
          <h1>Favorites! I am not sure how much more Ill do this.</h1>
          <p>May have to start a new project if I do not get paid.</p>
          I really need to find a project
          <!-- maybe a dnd app? -->
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    return {

    }
  }
}
</script>

<style scoped lang="scss">
.home {
  display: grid;
  height: 80vh;
  place-content: center;
  text-align: center;
  user-select: none;

  .home-card {
    width: clamp(500px, 50vw, 100%);

    >img {
      height: 200px;
      max-width: 200px;
      width: 100%;
      object-fit: contain;
      object-position: center;
    }
  }
}

.grayBg {
  background-color: rgb(180, 180, 180);
  height: 55dvh;
}

.grayBg2 {
  background-color: rgb(180, 180, 180);
  height: 55dvh;
  width: 40dvw;
}
</style>
