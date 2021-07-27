<template>
  <v-card
    v-if="true"
    flat
  >
    <v-card-title>
      <h1 class="title font-weight-bold mb-1">
        {{ title }}
      </h1>
      <v-spacer />
      <slot name="actions" />
    </v-card-title>
    <v-card-text>
      <slot />
    </v-card-text>
    <v-spacer />
  </v-card>
  <div
    v-else
    class="mb-5"
  >
    <div class="title mb-5">
      <h1>
        {{ title }}
      </h1>
      <template v-if="$slots.actions">
        <v-spacer />
        <slot name="actions" />
        <v-spacer />
      </template>
    </div>
    <slot />
  </div>
</template>

<script>
export default {
  name      : 'ContentSection',
  components: { },
  props     : { title: { type: String, default: '' } },
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
</style>
