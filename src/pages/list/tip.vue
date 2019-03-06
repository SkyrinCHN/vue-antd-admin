<template>
<!-- 点击新建弹出层 -->
<div id="components-form-demo-advanced-search" >
    <a-form class="ant-advanced-search-form">
      <a-row :gutter="24">
        <a-col
          v-for="(item,i) in title"
          :key="i"
          :span="6"
          :style="{ display: i < count ? 'block' : 'none' }"
        >
          <a-form-item >
            <a-input :placeholder='item'/>
          </a-form-item>
        </a-col>
      </a-row>
      <a-row>
        <a-col :span="24" :style="{ textAlign: 'right' }">
          <a-button type="primary">确定</a-button>
          <a-button :style="{ marginLeft: '8px' }">取消</a-button>
        </a-col>
      </a-row>
    </a-form>
  </div>
</template>
<script>

export default {
  data () {
    return {
      title:[
        '姓名','地址','联系电话','居住地址'
      ],
    }
  },
  computed: {
    count () {
      return this.expand ? 11 : 7
    }
  }
}
</script>
<style>
.input{
  display: inline;
}
.ant-advanced-search-form {
  padding: 24px;
  background: #fbfbfb;
  border: 1px solid #d9d9d9;
  border-radius: 6px;
}

.ant-advanced-search-form .ant-form-item {
  display: flex;
}

.ant-advanced-search-form .ant-form-item-control-wrapper {
  flex: 1;
}

#components-form-demo-advanced-search {
  max-width: none;
}
