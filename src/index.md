---
layout: false
---

<script setup lang="ts">
import { onMounted } from 'vue';

const supportedLanguages = ['cs', 'en'];

onMounted(() => {
  const preferredLanguage = window.navigator.language.toLowerCase();
  const matchingLanguage = supportedLanguages.find(lang => preferredLanguage.startsWith(lang));

  if (matchingLanguage) {
    // Change the path to the matched language version
    window.location.replace(`/${matchingLanguage}/`);
  } else {
    // Fallback to the default version if no match is found
    window.location.replace(`/${supportedLanguages[0]}/`);
  }
});
</script>
