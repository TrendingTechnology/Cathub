<template>
  <div class="">
    <div class="card">
      <div class="card-content">
        <div class="d-flex justify-space-between">
          <NuxtLink
            :to="`/archive/${category.name}`"
            class="text-h6 pinned-link"
            >{{ category.name }}</NuxtLink
          >
        </div>
        <div class="mb-3 desc color_secondary">
          {{ category.description }}
        </div>
        <div class="d-flex subdesc color_secondary">
          <div>{{ category.createdAt }}</div>
        </div>
      </div>
      <div class="card-img">
        <CommitBox />
      </div>
    </div>
    <v-divider class="mt-5 mb-5"></v-divider>
  </div>
</template>

<script>
export default {
  props: {
    category: {
      type: Object,
      default: () => ({})
    }
  }
};
</script>

<style lang="scss" scoped>
.pinned-link {
  color: #0366d6 !important;
  font-weight: 700 !important;

  :hover {
    cursor: pointer;
  }
}
.pinned-link:hover {
  cursor: pointer;
  text-decoration: underline;
}

.desc {
  font-size: 0.9rem;
}
.subdesc {
  font-size: 0.8rem;
}

.card {
  display: flex;
  justify-content: space-between;
}

.card-content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-img {
}

@media (max-width: $vt_sm) {
  .card-img {
    display: none;
  }
}
</style>
