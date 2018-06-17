<template>
  <div class="main-container d-flex">
    <div class="sidebar">
      <div class="sidebar-container">
        <div class="sidebar-box">
          <div class="title">
            <span>Location</span>
          </div>
          <select class="select-box">
            <option selected value="" v-for="part in data">{{ part.Zone }}</option>
          </select>
        </div>
        <div class="sidebar-box">
          <div class="title">
            <span>Date</span>
          </div>
          <div class="date-box">
            <span class="date-title ">from</span>
            <input type="text" name="" placeholder="2018/5/24" class="date-input ">
          </div>
          <div class="date-box">
            <span class="date-title ">to</span>
            <input type="text" name="" placeholder="2018/6/1" class="date-input ">
          </div>
        </div>
        <div class="sidebar-box">
          <div class="title">
            <span>Categories</span>
          </div>
          <div class="check-item">
            <input type="checkbox" name="">
            <span>All</span>
          </div>
          <div class="check-item">
            <input type="checkbox" name="">
            <span>Entertainment</span>
          </div>
          <div class="check-item">
            <input type="checkbox" name="">
            <span>Food</span>
          </div>
          <div class="check-item">
            <input type="checkbox" name="">
            <span>Learning</span>
          </div>
          <div class="check-item">
            <input type="checkbox" name="">
            <span>Outdoors</span>
          </div>
        </div>
      </div>
    </div>
    <div class="main-content">
      <div class="result-title">
        Showing<span>15</span>results by...
      </div>
      <div class="tags">
        <button class="btn">Kaohsiung<i class="far fa-times-circle"></i></button>
        <button class="btn">Kaohsiung<i class="far fa-times-circle"></i></button>
      </div>
      <Item v-for="part in data" :item ="part"></Item>
    </div>
  </div>
</template>
<script>
import Item from './Item'
import axios from 'axios'

export default {
  name: 'Search',
  data() {
    return {
      data: [],
    }
  },
  components: {
    Item
  },
  methods: {
    getData(keyword, page) {
      axios.get('https://data.kcg.gov.tw/api/action/datastore_search?resource_id=92290ee5-6e61-456f-80c0-249eae2fcc97&q='+keyword+'&limit='+page)
      .then((response) => {
        this.data = response.data.result.records
        console.log(response.data.result.records[0])

      })
      .catch((error) => {
        console.log(error)
      })
    }
  },
  created() {
    this.getData('',30)
  }
}
</script>
<style scoped>
.main-container {
  background: var(--lighter-grey);
}
.sidebar {
  margin-left: 38px;
}  
.sidebar-box {
  background: var(--light-grey);
  border-bottom: 1px solid var(--dark-grey);
  padding: 24px 40px;
}
.title {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 8px;
}
.select-box {
  border: none;
  border-radius: 2px;
  width: 220px;
  height: 40px;
  background: #fff;
}
.date-title {
  /*margin-right: 13px;*/
  font-size: 16px;
}
.date-input {
  width: 169px;
  height: 40px;
  border: none;
}
.date-box {
  text-align: right;
  margin-bottom: 8px;
}
.main-content {
  padding: 24px 42px;
}
.result-title {
  font-size: 24px;
  line-height: 28px;
}
.result-title span {
  color: var(--sec-color);
  padding: 0 8px;
  font-weight: bold;
  padding-bottom: 8px;
}
.tags {
  margin-top: 8px;
}
.tags button {
  border-radius: 100px;
  color: var(--sec-color);
  border: 1px solid var(--sec-color);
  background: none;
  font-style: italic;
  margin-right: 8px;
}
.tags i {
  margin-left: 8px;
}
</style>