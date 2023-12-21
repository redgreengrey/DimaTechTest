<template>
  <div class="menu">
    <NuxtLink to="/" class="menu-item">Меню</NuxtLink>
    <div class="delimiter"></div>
    <NuxtLink to="/delivery" class="menu-item">Доставка</NuxtLink>
    <div class="delimiter"></div>
    <NuxtLink to="/promotion" class="menu-item">Акции</NuxtLink>
    <div class="delimiter"></div>
    <NuxtLink to="/review" class="menu-item">Отзывы</NuxtLink>
    <div class="delimiter"></div>
    <NuxtLink to="/contacts" class="menu-item">Контакты</NuxtLink>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.menu {
    display: inline-flex;
    align-items: center;
    gap: 16px;
}

.menu-item {
    color: #ffffff;
    font-family: Neucha;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 20px;
    letter-spacing: 0.8px;
    text-decoration: none;
}

.delimiter {
    width: 3px;
    height: 3px;
    border-radius: 50%;
    background: #ffffff;
}
</style>