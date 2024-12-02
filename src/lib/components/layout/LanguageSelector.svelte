<script lang="ts">
  import { goto } from "$app/navigation";
  import { page } from "$app/stores";

  import { Globe } from "lucide-svelte";

  import { i18n } from "$lib/i18n";
  import { type AvailableLanguageTag } from "$paraglide/runtime";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
  import { buttonVariants } from "$components/ui/button";

  function switchToLanguage(newLang: string) {
    const canonicalPath = i18n.route($page.url.pathname);
    const localisedPath = i18n.resolveRoute(
      canonicalPath,
      newLang as AvailableLanguageTag
    );
    goto(localisedPath);
  }

  const languages = [
    {
      label: "English",
      value: "en",
    },
    {
      label: "Español",
      value: "es",
    },
  ];
</script>

<DropdownMenu.Root>
  <DropdownMenu.Trigger
    class={`${buttonVariants({ variant: "outline" })} flex items-center`}
  >
    <Globe /> Language
  </DropdownMenu.Trigger>
  <DropdownMenu.Content class="w-56">
    <DropdownMenu.Group>
      {#each languages as { label, value } (value)}
        <DropdownMenu.Item onclick={() => switchToLanguage(value)}>
          {label}
        </DropdownMenu.Item>
      {/each}
    </DropdownMenu.Group>
  </DropdownMenu.Content>
</DropdownMenu.Root>
