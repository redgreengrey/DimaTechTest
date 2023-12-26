<template>
  <div class="main">
    <div class="title">
      <div class="dot"></div>
      <div class="text">МЕНЮ</div>
      <div class="dot"></div>
    </div>

    <Tabs class="tabs">
      <Tab name="роллы"> </Tab>
      <Tab name="суши и гунканы"> </Tab>
      <Tab name="сеты"> </Tab>
      <Tab name="лапша и рис" :selected="true">
        <Card
          :count="0"
          rollName="РОЛЛ ЯСАЙ"
          :img="'/img/ролл ясай 1.png'"
          :isFavorite="false"
          rollDesc="Огурец, авокадо, помидор, болгарский перец, листья салата, кунжут"
          :price="200"
          :weight="185"
        />
      </Tab>
      <Tab name="салаты"> </Tab>
      <Tab name="горячие блюда"> </Tab>
    </Tabs>
  </div>
</template>

<script>
import Tabs from "~/components/Tabs/Tabs.vue";
import Tab from "~/components/Tabs/Tab.vue";
import Card from "~/components/Card.vue";

export default {
  name: "IndexPage",
  components: {
    Tabs,
    Tab,
    Card,
  },
};
</script>

<style>
.main {
  margin-top: 100px;
  margin-left: 375px;
  margin-right: 375px;
}

.title {
  width: 240px;
  height: 66px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 auto;
  color: #312525;
  font-family: Neucha;
  font-size: 60px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  padding-bottom: 50px;
}

.dot {
  background: #312525;
  width: 10px;
  height: 10px;
  border-radius: 50%;
}

.tabs {
  padding-bottom: 60px;
}
</style>
