<template>
  <div class="m-4">
    <b-jumbotron bg-variant="dark" text-variant="white" border-variant="dark">
      <template #header>Binary Search Algorithm</template>

      <template #lead>
        also known as half-interval search, logarithmic search, or binary chop, is a search algorithm that finds the
        position of a target value within a sorted array.
        <br>
        Binary search compares the target value to the middle element of the array.
      </template>
      <p class="fw-bold">
        <span class="fw-light">languages : VueJS / HTML / CSS (Bootstrap)</span>
        <br>
        Create By : Reza Some / Ali Mashkani
      </p>
      <hr class="mt-5 mb-4">

      <div class="mb-3">
        <h5 for="exampleFormControlInput1" class="fw-bold form-label">Enter The List Of Numbers :</h5>
        <input v-model="newList" type="text" class="form-control mb-1 fw-bold bg-secondary p-2 text-white bg-opacity-25" id="exampleFormControlInput1" placeholder="example : 1,2,3,4,5,6">
        <p class="fw-light">
          (If the values left blank, the default list is used)
          <br>
          default list : {{list}}
        </p>
      </div>
      <div class="mb-3">
        <h5 for="exampleFormControlInput1" class="fw-bold form-label">Enter The Number You Want To Search :</h5>
        <input v-model="value" type="text" class="form-control mb-1 fw-bold bg-secondary p-2 text-white bg-opacity-25" id="exampleFormControlInput1" placeholder="example : 13">
      </div>
      <modal :counter="counter" :value="value" :pos="pos"></modal>
      <b-button id="show-btn" @click="createList()" style="padding: 11px 0" class="w-100 fw-bold mt-3">Start Searching...</b-button>
    </b-jumbotron>
  </div>
</template>

<script>
import Modal from './Modal.vue'
export default {
  components: { Modal },
  data(){
    return{
      newList: '',
      list: [3,4,7,9,13,45,55,56,59,61,66],
      value: '',
      pos: null,
    }
  },
  methods: {
    createList(){
      if(isNaN(Number(this.value)) || this.value === ''){
        alert('لطفا مقدار عددی صحیح وارد نمایید...')
        return false
      }
      if(this.newList === ''){
        this.binarySearch(this.value,this.list)
      } else{
        this.binarySearch(this.value,this.newList.split(','))
      }
    },
    binarySearch(value,list) {
      let first = 0;
      let last = list.length - 1;
      let position = -1;
      let found = false;
      let middle;
      while (found === false && first <= last) {
        middle = Math.floor((first + last) / 2);
        if (list[middle] == value) {
          found = true;
          position = middle;
        } else if (list[middle] > value) {
          last = middle - 1;
        } else {
          first = middle + 1;
        }
      }
      this.pos = position;
      this.$bvModal.show('bv-modal-example')
    }
  }
}
</script>

<style>

</style>