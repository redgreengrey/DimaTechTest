<template>
  <div class="header">
    <Logo />
    <Menu class="menu" />
    <Phone class="phone" />
    <button class="btn-cart"><img src="/svg/icon-cart.svg"></button>
    <button class="btn-login">Войти</button>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import Menu from '~/components/Menu.vue'
import Phone from '~/components/Phone.vue'

export default {
  componenets: {Logo, Menu, Phone}
}
</script>

<style>
.header {
  background: #062D4E;
  height: 82px;
  width: 100%;
  display: flex;
  padding: 0 370px;
}

.menu {
  margin-left: 70px;
}

.phone {
  margin-left: 80px;
}

.btn-cart {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background: #ffffff;
  align-self: center;
  margin-left: 150px;
  cursor: pointer;
}

.btn-login {
  width: 101px;
  height: 42px;
  display: inline-flex;
  padding: 12px 30px 10px 30px;
  justify-content: center;
  align-items: center;
  gap: 10px;
  border-radius: 30px;
  background: #ffffff;
  align-self: center;
  margin-left: 24px;
  cursor: pointer;
  font-family: Neucha;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: 0.8px;
}
</style>