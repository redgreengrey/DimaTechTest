<template>
  <div class="logo">
    <div v-if="window.width > 980" class="big">
        <div class="eclipse">
            <img src="/img/logoBig.png" />
        </div>
    </div>
    <div v-else class="small">
        <img src="/img/logoSmall.png" />
    </div>
  </div>
</template>

<script>
export default {
name: "Logo",

data: () => ({
    window: {
        width: 0,
        height: 0
    }
}),

created() {
    window.addEventListener('resize', this.handleResize);
    this.handleResize();
},

destroyed() {
    window.removeEventListener('resize', this.handleResize);
},

methods: {
    handleResize() {
        this.window.width = window.innerWidth;
        this.window.height = window.innerHeight;
    }
}
}
</script>

<style>
.eclipse {
  display: flex;
  align-items: center;
  justify-content: center;
  background: #ffffff;
  border-radius: 50%;
  width: 182px;
  height: 182px;
  margin-top: 20px;
}

</style>