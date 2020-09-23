<template>
  <yearpick-it v-if="type=='year'" v-bind="$attrs" v-on="$listeners"/>
  <monthpick-it v-else-if="type=='month'" v-bind="$attrs" v-on="$listeners"/>
  <datepick-it v-else-if="type=='date'" v-bind="$attrs" v-on="$listeners"/>
</template>
<script>
export default {
  name: 'DatepickItWrapper',
  inheritAttrs: false,
  props: {
    type: {
      type: String,
      validator: type => {
        return ['date', 'month', 'year'].includes(type)
      }
    }
  }
}
</script>