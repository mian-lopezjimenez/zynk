<script lang="ts">
  import { ParaglideJS } from "@inlang/paraglide-sveltekit";

  import { i18n } from "$lib/i18n";
  import { Header } from "$components/layout";

  let { children } = $props();
</script>

<ParaglideJS {i18n}>
  <Header />
  {@render children()}
</ParaglideJS>
