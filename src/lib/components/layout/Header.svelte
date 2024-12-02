<script lang="ts">
  import { ThemeSwitch, LanguageSelector } from "$components/layout";

  import logo from "$assets/zynk-logo.svg";
</script>

<header>
  <img src={logo} alt="Zynk Logo" />
  <div class="right">
    <LanguageSelector />
    <ThemeSwitch />
  </div>
</header>

<style>
  header {
    display: flex;
    justify-content: space-between;
    padding: 1rem;
  }

  .right {
    display: flex;
    gap: 1rem;
  }

  header img {
    width: 40px;
    height: 40px;
  }
</style>
