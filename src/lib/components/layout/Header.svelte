<script lang="ts">
  import { goto } from "$app/navigation";
  import { page } from "$app/stores";

  import { i18n } from "$lib/i18n";

  import {
    type AvailableLanguageTag,
    availableLanguageTags,
    languageTag,
  } from "$paraglide/runtime";

  function switchToLanguage(event: Event) {
    const { value } = event.target as HTMLSelectElement;
    const canonicalPath = i18n.route($page.url.pathname);
    const localisedPath = i18n.resolveRoute(
      canonicalPath,
      value as AvailableLanguageTag
    );
    goto(localisedPath);
  }

  const labels = {
    en: "English",
    es: "Español",
  };
</script>

<select onchange={switchToLanguage}>
  {#each availableLanguageTags as langTag}
    <option value={langTag} selected={languageTag() === langTag}
      >{labels[langTag]}</option
    >
  {/each}
</select>
