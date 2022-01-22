<template>
  <div class="m-4">
    <b-jumbotron bg-variant="dark" text-variant="white" border-variant="dark">
      <template #header>
        Merge Sort Algorithm
      </template>

      <template #lead>
        merge sort  is an efficient, general-purpose, and comparison-based sorting algorithm.
        <br>
        Most implementations produce a stable sort, which means that the order of equal elements is the same in the input and output.
        <br />
        Merge sort is a divide and conquer algorithm that was invented by John von Neumann in 1945.
      </template>
      <p class="fw-bold">
        <span class="fw-light">languages : VueJS / HTML / CSS (Bootstrap)</span>
        <br />
        Create By : Reza Some / Ali Mashkani
      </p>
      <hr class="mt-5 mb-4" />

      <div class="mb-3">
        <h5 for="exampleFormControlInput1" class="fw-bold form-label">
          Enter The List Of Numbers :
        </h5>
        <input v-model="array" 
            type="text" 
            class="
            form-control
            mb-1
            fw-bold
            bg-secondary
            p-2
            text-white
            bg-opacity-25" 
            id="exampleFormControlInput1" 
            placeholder="example : 1,34,2,33,15,26" />
      </div>
      
      <b-button id="show-btn" @click="createList()" style="padding: 11px 0" class="w-100 fw-bold mt-3 mb-2">
        Start Searching...
      </b-button>

      <hr>

      <b-button v-if="res.length !== 0" dir="rtl" style="width: 100%;font-weight: bold; font-size: 18px;padding-bottom: 20px !important;" v-b-toggle.collapse-3 class="mb-2 mt-1 py-3 ttt">
        آرایه مرتب شده : 
        <span dir="ltr">
          {{ res }}
        </span>
      </b-button>
      <b-collapse visible id="collapse-3">
        <div class="my-2 mx-3" v-html="steps"></div>
      </b-collapse>

    </b-jumbotron>
  </div>
</template>

<script>
export default {
  data() {
    return {
      array: '2,5,1,3,4,9,8,6',
      finalArr: [],
      steps: '',
      res: []
    };
  },
  methods: {
    createList() {
      if (this.array === '') {
        alert("لطفا مقدار عددی صحیح وارد نمایید...");
        return false;
      }
      this.steps = '';
      this.res = [];
      this.finalArr = [];

      let arr = this.array.split(",");
      arr.map(el => {
        this.finalArr.push(Number(el))
      })
      this.res = this.mergeSort(this.finalArr)
    },

    mergeSort(array) {
      // Base case or terminating case
      if (array.length < 2) {
        return array
      }
      const half = Math.floor(array.length / 2)
      const right = array.splice(half, array.length - 1)
      const left = array.splice(0, half)

      this.steps += `<p style="background: rgba(255,255,255,.15); padding:5px 10px; font-weight: bold; border-radius: 3px">left: ${left} - right: ${right}</p>`;
      
      return this.merge(this.mergeSort(left), this.mergeSort(right))
    },
    
    merge(left, right) {
      let arr = []

      this.steps += `<p style="background: rgba(255,255,255,.3); padding:5px 10px; font-weight: bold; border-radius: 3px">left: ${left} - right: ${right}</p>`;
      
      // Break out of loop if any one of the array gets empty
      while (left.length && right.length) {
        // Pick the smaller among the smallest element of left and right sub arrays 
        if (left[0] < right[0]) {
            arr.push(left.shift())
        } else {
            arr.push(right.shift())
        }
      }
      // Concatenating the leftover elements
      // (in case we didn't go through the entire left or right array)
      return [...arr, ...left, ...right]
    }
  },
};
</script>
