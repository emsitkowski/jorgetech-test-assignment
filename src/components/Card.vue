<template>
  <div class="card">
    <!-- Image -->
    <div class="card__image">
      <slot name="image"></slot>
    </div>

    <!-- Content -->
    <div class="card__content">
      <!-- Title -->
      <h2 class="card__title text-secondary">
        <slot name="title"></slot>
      </h2>

      <!-- Slot -->
      <slot></slot>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;
  border-radius: 8px;
  background-color: #ffffff;
  overflow: hidden;
  @media (min-width: 1200px) {
    flex-direction: row;
  }

  & > * {
    flex-basis: 50%;
  }

  &__image {
    width: 100%;
    max-height: 200px;
    @media (min-width: 1200px) {
      max-height: unset;
    }

    :deep img {
      width: 100%;
      height: 100%;
      max-width: 100%;
      object-fit: cover;
      object-position: center;
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
    gap: 12px;
    padding: 24px;
    @media (min-width: 1200px) {
      padding: 40px 30px 40px 34px;
    }
  }
}
</style>
