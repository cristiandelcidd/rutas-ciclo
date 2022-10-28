<template>
  <a v-if="isExternalLink" :href="link.to" target="_blank">{{ link.name }}</a>
  <router-link v-else :to="link.to" v-slot="{ href, isActive }"
    ><a :href="href" :class="isActive ? 'is-active' : 'normal-link'">{{
      link.name
    }}</a></router-link
  >
</template>

<script>
export default {
  props: {
    link: {
      type: Object,
      required: true,
    },
  },
  computed: {
    isExternalLink() {
      return this.link.to.startsWith("http");
    },
  },
};
</script>

<style scoped>
a,
a:active {
  color: #000;
  text-decoration: none;
}

.is-active {
  color: #42b983;
  text-decoration: underline;
}

.normal-link {
  color: #686868;
}
</style>
