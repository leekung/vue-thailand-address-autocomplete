<template>
  <div id="app">
    <a href="https://github.com/biigpongsatorn/vue-thailand-address-autocomplete">
      <h1>vue-thailand-address-autocomplete</h1>
    </a>
    <ThailandAutoComplete
      v-model="district"
      :value="district"
      class="form-control"
      type="district"
      @select="select"
      label="ตำบล"
      color="#42b883"
      size="small"
      placeholder="ตำบล..."
    />
    <ThailandAutoComplete v-model="amphoe" :value="amphoe" class="form-control" type="amphoe" @select="select" label="อำเภอ" placeholder="อำเภอ..."/>
    <ThailandAutoComplete v-model="province" :value="province" class="form-control" type="province" @select="select" label="จังหวัด" size="medium" color="#35495e" placeholder="จังหวัด..."/>
    <ThailandAutoComplete v-model="zipcode" :value="zipcode" class="form-control" type="zipcode" @select="select" label="รหัสไปรษณีย์" size="large" color="#00a4e4" placeholder="รหัสไปรษณีย์..."/>
  </div>
</template>

<script>
// import ThailandAutoComplete from '../dist/vue-thailand-address-autocomplete.min.js'
import ThailandAutoComplete from '../src/vue-thailand-address-autocomplete.vue'

export default {
  name: 'app',
  data () {
    return {
      district: 'สิชล',
      amphoe: '',
      province: '',
      zipcode: ''
    }
  },
  methods: {
    select (address) {
      this.district = address.district
      this.amphoe = address.amphoe
      this.province = address.province
      this.zipcode = address.zipcode
    }
  },
  components: {
    ThailandAutoComplete
  }
}
</script>

<style scoped>
* {
  box-sizing: border-box;
}
h1 {
  font-family: Arial, Helvetica, sans-serif;
}
#app {
  width: 50vw;
  margin: 0 auto;
}
.card {
  float: left;
  width: 100%;
  padding: 25px;
  border: 1px solid #ccc;
  text-align: center;
  margin-bottom: 25px;
}

@media only screen and (max-width: 768px) {
  #app {
    width: 80vw;
    margin: 0 auto;
  }
}
</style>
