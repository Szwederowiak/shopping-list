<template>
  <li class="d-flex justify-content-between align-items-center mb-1 p-2 bg-dark bg-opacity-10 rounded-3">
      {{ content }}
      <button @click="sendIdToDelete" class="btn btn-danger btn-sm rounded-2">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-trash-fill"
              viewBox="0 0 16 16">
              <path
                  d="M2.5 1a1 1 0 0 0-1 1v1a1 1 0 0 0 1 1H3v9a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2V4h.5a1 1 0 0 0 1-1V2a1 1 0 0 0-1-1H10a1 1 0 0 0-1-1H7a1 1 0 0 0-1 1H2.5zm3 4a.5.5 0 0 1 .5.5v7a.5.5 0 0 1-1 0v-7a.5.5 0 0 1 .5-.5zM8 5a.5.5 0 0 1 .5.5v7a.5.5 0 0 1-1 0v-7A.5.5 0 0 1 8 5zm3 .5v7a.5.5 0 0 1-1 0v-7a.5.5 0 0 1 1 0z" />
          </svg>
      </button>
  </li>
</template>

<script>
export default {
  props: {
      id: {
          type: Number,
          required: true
      },
      content: {
          type: String,
          required: true
      }
  },
  methods: {
      sendIdToDelete() {
          this.$emit("delete-id", this.id)
      }
  }
}
</script>