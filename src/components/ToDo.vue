<script>
export default {
  data() {
    return {
      list: [{ item: "", quantity: 0, done: false }],
    };
  },
  methods: {
    add() {
      this.list.push(this.list);
    },
    remove(e) {
      this.list.splice(e, 1);
    },
  },
};
</script>

<template>
  <div class="container">
    <h1>Simple list</h1>
    <div class="col-md-12 row" v-for="(l, index) in list" :key="index">
      <div class="col-md-4">
        <input
          type="text"
          class="form-control"
          placeholder="Item"
          v-model="l.item"
        />
      </div>
      <div class="col-md-3">
        <input
          type="text"
          class="form-control"
          placeholder="quanity"
          v-model="l.quantity"
        />
      </div>
      <div class="col-md-3">
        <input
          type="checkbox"
          class="form-check-input"
          placeholder="done"
          v-model="l.done"
        />
      </div>
      <div class="col-md-2">
        <div class="button-group"></div>
        <button type="button" @click="add" class="btn btn-primary btn-sm">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="16"
            height="16"
            fill="currentColor"
            class="bi bi-plus"
            viewBox="0 0 16 16"
          >
            <path
              d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z"
            />
          </svg>
        </button>
        <button type="button" @click="remove(index)" class="btn-danger btn-sm">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="16"
            height="16"
            fill="currentColor"
            class="bi bi-dash"
            viewBox="0 0 16 16"
          >
            <path
              d="M4 8a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7A.5.5 0 0 1 4 8z"
            />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<style>
</style>
