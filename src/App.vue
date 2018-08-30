<template>
  <div>
    <pagination :totalPages="12"/>
  </div>
</template>
<script>
import pagination from './pagination/pagination.vue'
export default {
  components : {
    pagination
  }
}
</script>
