<script lang="ts">
    import { isPreviewing, Content } from "@builder.io/sdk-svelte";
    import { CUSTOM_COMPONENTS } from '../../registerComponents/componentsRegistry'
 
      // this data comes from the function in `+page.server.js`, which runs on the server only
      export let data;
 
    // we want to show unpublished content when in preview mode.
    const canShowContent = data.content || isPreviewing();
  </script>
 
  <main>
    {#if canShowContent}
      <Content
        enrich={true}
        model="symbol"
        content={data.content}
        apiKey={import.meta.env.VITE_BUILDER_PUBLIC_API_KEY}
        customComponents={CUSTOM_COMPONENTS}
      />
    {:else}
      Content Not Found
    {/if}
  </main>