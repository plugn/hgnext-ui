<template>

  <DxBox
    :height="250"
    direction="col"
    width="100%"
    style="flex: 1;"
  >
    <DxItem
      :ratio="1"
    >
      <template #default>
        <div class="rect demo-dark header">Header</div>
      </template>
    </DxItem>
    <DxItem
      :ratio="2"
      :base-size="0"
    >
      <DxBox
        :height="125"
        direction="row"
        width="100%"
      >
        <DxItem :ratio="1">
          <template #default>
            <div class="rect demo-dark">Left Bar</div>
          </template>
        </DxItem>
        <DxItem :ratio="1">
          <template #default>
            <div class="rect demo-light">Content</div>
          </template>
        </DxItem>
        <DxItem :ratio="1">
          <template #default>
            <div class="rect demo-dark">Right Bar</div>
          </template>
        </DxItem>
      </DxBox>
    </DxItem>
    <DxItem :ratio="1">
      <template #default>
        <div class="rect demo-dark footer">Footer</div>
      </template>
    </DxItem>
  </DxBox>
</template>

<script>
  import 'devextreme/dist/css/dx.light.css'
  import {DxBox, DxItem} from 'devextreme-vue/box'

  export default {
    name: 'toolbox',
    components: {
      DxBox,
      DxItem,
    }
  }
</script>

<style scoped>
  .rect {
    text-align: center;
    font-size: 30px;
    padding-top: 10px;
    height: 100%;
  }

  .demo-light {
    background: rgba(245, 229, 166, 0.5);
  }

  .demo-dark {
    background: rgba(148, 215, 199, 0.5);
  }

  .demo-dark.header {
    background: rgba(243, 158, 108, 0.5);
  }

  .demo-dark.footer {
    background: rgba(123, 155, 207, 0.5);
  }

  .small {
    height: 50px;
    border: 1px solid lightgray;
  }
</style>
