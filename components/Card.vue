<template>
  <div class="card" :class="{ 'card-dark': isInCart }">
    <div class="card-header">
      <img :src="img" alt="" />
      <div
        @click="isFavorite = !isFavorite"
        class="heart"
        :class="{ 'card-dark-heart': isInCart }"
      >
        <img v-if="isFavorite" src="/svg/heart.svg" alt="fav" />
        <EmptyHeartSVG v-else />
      </div>
    </div>
    <div class="card-body">
      <div class="card-body__top">
        <div class="name" :class="{ 'card-dark': isInCart }">
          {{ rollName }}
        </div>
        <div class="weight" :class="{ 'card-dark': isInCart }">
          {{ weight }}
        </div>
      </div>
      <div class="card-body__bottom" :class="{ 'card-dark': isInCart }">
        {{ rollDesc }}
      </div>
    </div>
    <div class="card-footer">
      <div class="price">{{ price }} <span class="rubble-sign">₽</span></div>
      <div class="roll-count">
        <button v-if="count < 1" @click="count = 1" class="btn-to-cart">
          В корзину
        </button>
        <div v-else class="roll-count">
          <div @click="count--" class="minus">
            <img src="/svg/minus.svg" alt="" />
          </div>
          <div class="count">{{ count }}</div>
          <div @click="count++" class="plus">
            <img src="/svg/plus.svg" alt="" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import EmptyHeartSVG from "~/components/EmptyHeartSVG.vue";

export default {
  name: "Card",

  components: { EmptyHeartSVG },

  props: {
    count: Number,
    rollName: String,
    rollDesc: String,
    weight: Number,
    price: Number,
    isFavorite: Boolean,
    img: String,
  },

  data: () => ({
    // count: 0,
    // weight: 230,
    // isFavorite: false,
  }),

  computed: {
    isInCart() {
      return this.count > 0;
    },
  },
};
</script>

<style scoped>
.card {
  width: 270px;
  height: 390px;
  border-radius: 8px;
  background: #fafafa;
  box-shadow: 0px 0px 12px 0px rgba(0, 0, 0, 0.25);
  padding: 30px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-header {
  padding: 0px 30px 0px 40px;
  display: flex;
  align-items: flex-start;
}

.heart {
  padding-left: 20px;
  cursor: pointer;
}

.card-body {
  /* padding-bottom: 45px; */
}

.card-body__top {
  display: flex;
  justify-content: space-between;
  padding-bottom: 20px;
}

.name {
  color: #141414;
  font-family: Neucha;
  font-size: 19px;
  font-style: normal;
  font-weight: 400;
  line-height: 25px;
  letter-spacing: 1.9px;
  text-transform: uppercase;
}

.weight {
  color: #808080;
  font-family: "Arial Narrow";
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  letter-spacing: 0.52px;
}

.card-body__bottom {
  color: #808080;
  font-family: Arial;
  font-size: 15px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  letter-spacing: 0.6px;
  display: flex;
  flex-wrap: wrap;
}

.card-footer {
  display: flex;
  justify-content: space-between;
}

.price {
  /* color: #FFF; */
  font-family: Neucha, sans-serif;
  font-size: 19px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  letter-spacing: 0.95px;
}

.rubble-sign {
  font-family: Neucha, sans-serif;
}

.btn-to-cart {
  width: 100px;
  height: 35px;
  border-radius: 8px;
  background: #312525;
  box-shadow: 0px 0px 12px 0px rgba(0, 0, 0, 0.35);
  align-self: center;
  cursor: pointer;
  color: #ffffff;
  font-family: "Montserrat";
  font-size: 11px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
}

.roll-count {
  width: 94px;
  height: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 13px;
}

.minus,
.plus {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
}

.count {
  color: #fff;
  font-family: Neucha;
  font-size: 19px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  letter-spacing: 0.95px;
}

.card-dark {
  background: #312525;
  color: #ffffff;
}

.card-dark-heart {
  color: #ffffff;
}
</style>
