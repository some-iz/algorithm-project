<template>
  <b-modal body-text-variant="light" header-text-variant="light" header-bg-variant="secondary" body-bg-variant="secondary" id="bv-modal-example" hide-footer>
    <template #modal-title>
      Binary Search Result
    </template>
    <div class="d-block text-center py-5">
      <h5 dir="rtl">
        عدد
        {{value}}
        در لیست اعداد موجود
        {{pos === -1 ? 'نمی باشد.' 
        : 'می باشد.'}}
      </h5>
      <hr v-if="pos !== -1">
      <h6 v-if="pos !== -1">
        موقعیت درون آرایه : 
        {{pos}}
      </h6>
    </div>
    <b-button class="mt-2 w-100 bg-dark" block @click="$bvModal.hide('bv-modal-example')">Close Modal...</b-button>
  </b-modal>
</template>

<script>
export default {
    props: ['value' , 'pos']
}
</script>

<style>
.close{
    background: transparent;
    border: 0;
    font-size: 23px;
    font-weight: bold;
    transform: translateY(-2px);
}
h5,h6{
    font-family: 'iranSans';
} 
</style>