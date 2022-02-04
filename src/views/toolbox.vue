<template>
  <div style="flex-direction: column; flex: 1;">
    <DxTabPanel
      :selected-index="selectedTabIndex"
    >
      <DxItem title="Employee" icon="floppy">
        <template #default>
          <DxForm :form-data="employeeData">
            <DxSimpleItem data-field="name"/>
            <DxSimpleItem data-field="position"/>
            <DxSimpleItem data-field="hireDate"/>
            <DxSimpleItem data-field="officeNumber"/>
          </DxForm>
        </template>
      </DxItem>

      <DxItem title="Notes" icon="comment">
        Notes
      </DxItem>
      <DxItem title="Role" icon="isnotblank" badge="new">
        Role
      </DxItem>
    </DxTabPanel>
    <DxRadioGroup
      :items="tabNames"
      :value="tabNames[selectedTabIndex]"
      layout="horizontal"
      @value-changed="onValueChanged"
    />
  </div>
</template>

<script>
  import DxTabPanel, {DxItem} from 'devextreme-vue/tab-panel'
  import DxRadioGroup from 'devextreme-vue/radio-group'
  import DxForm, {DxSimpleItem} from 'devextreme-vue/form'

  // import 'devextreme/dist/css/dx.light.css'
  // import {DxBox, DxItem} from 'devextreme-vue/box'
  // import DxTextArea from 'devextreme-vue/text-area'

  export default {
    name: 'toolbox',
    components: {
      // DxBox,
      DxItem,
      DxTabPanel,
      DxRadioGroup,
      DxForm,
      DxSimpleItem,
    },
    data() {
      const tabNames = ['Employee', 'Notes', 'Role']

      const employeeData = {
        name: 'John Heart',
        position: 'CEO',
        hireDate: new Date(2012, 4, 13),
        officeNumber: 901,
        notes: 'John has been in the Audio/Video industry since 1990. He has led DevAV as its CEO since 2003.',
        roles: ['Chief Officer', 'Administartor', 'Manager']
      }

      return {
        employeeData,
        selectedTabIndex: 0,
        tabNames,
      }
    },
    methods: {
      onValueChanged(e) {
        this.selectedTabIndex = this.tabNames.indexOf(e.value)
      }
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
