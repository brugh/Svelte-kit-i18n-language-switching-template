<script context="module" lang="ts">
  import { _, addMessages, init, locale, getLocaleFromNavigator } from "svelte-i18n";
  import en from "../../lang/en.json";
  import _nl from "../../lang/nl.json";

  const nl = <{ [key: string]: string }>_nl; // ??? why not for 'en'

  addMessages("en", en);
  addMessages("nl", nl);

  export const initLang = (options = { lang: null}) => {
    let lang = options?.lang || getLocaleFromNavigator()?.replace("_", "-").split("-")[0] || '';
    if (!['en', 'nl'].includes(lang)) lang = 'nl';
    init({ initialLocale: lang, fallbackLocale: "en" });
  };
</script>

<button on:click={(ev) => locale.set("en")}>en</button>
<button on:click={(ev) => locale.set("nl")}>nl</button>
