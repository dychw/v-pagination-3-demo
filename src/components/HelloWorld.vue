<template>
  <pagination
    v-model="page"
    :options="{ template: MyPagination }"
    :per-page="PER_PAGE"
    :records="totalPages"
    @paginate="onPageClick"
  />
</template>

<script>
import { ref } from "vue";
import MyPagination from "@/components/MyPagination";
export default {
  name: "HelloWorld",
  setup() {
    const PER_PAGE = 3;
    const page = ref(1);
    const totalPages = ref(20);
    const onPageClick = (pageNumber) => {
      console.log(pageNumber);
    };
    return { totalPages, MyPagination, onPageClick, page, PER_PAGE };
  },
};
</script>

<style></style>
