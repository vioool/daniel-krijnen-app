<template>
    <div :to="to" class="dk-card">
      <!--    TODO: dk-card div vervangen voor route-link Tutorial: https://vueschool.io/lessons/adding-routes-and-content-->
      <pre> {{ entries }}</pre>
        <img class="dk-card__image" src="../assets/images/DK-Oostenburg.jpg" alt="">
        <div class="dk-card__body">
            <h2>{{ title }}</h2>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: null
    },
    to: {
      type: [Object, String],
      default: null
    }
  }
};
</script>

<style>
.dk-card {

  width: 15.5rem;
  height: 15.5rem;

  border: solid var(--color-grey-light) .0125rem;
}

.dk-card:hover {
  opacity: 0.5;
}

.dk-card__image {
  width: 15.5rem;
}

</style>
