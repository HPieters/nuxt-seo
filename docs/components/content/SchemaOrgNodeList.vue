<script lang="ts" setup>
import { schemaAutoImports } from '@unhead/schema-org/vue'

const nodes = schemaAutoImports.filter(s => s !== 'useSchemaOrg')

function normaliseToPath(s: string) {
  return s.replace('define', '').toLowerCase()
}
</script>

<template>
  <ul>
    <li v-for="(node, key) in nodes" :key="key">
      <a :href="`https://unhead.unjs.io/schema-org/schema/${normaliseToPath(node)}`">
        {{ node }}
      </a>
    </li>
  </ul>
</template>
