<template>
  <div>
    <div class="top">
      <div
        class="topline"
        style="width: 100%; height: 106px; background-color: blueviolet"
      ></div>
    </div>
    <div>
      <div class="container">
        <div class="data" style="height: 4000px">
          <ContentList></ContentList>
        </div>
        <div class="aside" style="display: flex">
          <AsideLine> </AsideLine>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AsideLine from "../components/AsideLine.vue";
import ContentList from "../components/contentList.vue";
export default {
  components: { AsideLine, ContentList },
};
</script>

<style>
.container {
  position: relative;
  margin: 0 auto;
  width: 100%;
  width: 960px;
  max-width: 960px;
}
.data {
  background-color: aqua;
  display: flex;
  margin-right: 21.667rem;
  border-radius: 2px;
  width: 700px;
}
</style>