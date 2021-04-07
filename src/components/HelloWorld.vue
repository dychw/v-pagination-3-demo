<template>
  <pagination
    v-model="page"
    :options="{ template: MyPagination }"
    :per-page="PER_PAGE"
    :records="totalPages"
    @paginate="onPageClick"
    ref="table"
  />
</template>

<script>
import { ref } from "vue";
import MyPagination from "@/components/MyPagination";
export default {
  name: "HelloWorld",
  // methods: {
  //   onPageClick: function() {
  //     this.$refs.table.setPage(1); // TypeError: this.$refs.table.setPage is not a function
  //   },
  // },
  setup() {
    const PER_PAGE = 3;
    const page = ref(1);
    const totalPages = ref(20);
    const table = ref(null);
    // const onPageClick = () => {
    //   table.value.setPage(1); // TypeError: table.value.setPage is not a function
    // };
    return { totalPages, MyPagination, page, PER_PAGE, table };
  },
};
</script>

<style></style>
