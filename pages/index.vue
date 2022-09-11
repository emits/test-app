<template>
  <div>
    <div class="container">
      <input v-model="name">
      <button @click="set()">保存</button>
    </div>
    <div class="container">
      <button @click="get()">表示</button>
    </div>
    <div>
      <p>{{info}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return {
      info: ""
    }
  },
  mounted () {
    this.interval()
  },
  methods: {
    interval(){
      setInterval(function () {
        this.name = localStorage.getItem('name')
        if(this.name !== this.info){
          // this.info = localStorage.getItem('name')
          // this.$router.go({path: this.$router.currentRoute.path, force: true})
        }
        // this.info = localStorage.getItem('name')
        console.log('hi') // eslint-disable-line no-console
      }.bind(this), 1000)
    },
    set() {
      localStorage.setItem('name', this.name)
    },
    get() {
      this.info = localStorage.getItem('name')
    }
  },
}

</script>
