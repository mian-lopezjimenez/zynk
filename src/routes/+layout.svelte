<script lang="ts">
  import { ParaglideJS } from "@inlang/paraglide-sveltekit";

  import { ModeWatcher } from "mode-watcher";

  import { i18n } from "$lib/i18n";
  import { Header } from "$components/layout";

  import "../app.css";

  let { children } = $props();
</script>

<ParaglideJS {i18n}>
  <ModeWatcher />
  <Header />
  {@render children()}
</ParaglideJS>
