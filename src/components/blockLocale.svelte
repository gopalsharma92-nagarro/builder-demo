<script lang="ts">
    import { selectedLanguage } from "./ProductCard/stores";
    let selected:string = "en-US";
    $:{selectedLanguage.set(selected)};
    $:{console.log("hello",$selectedLanguage)}
</script>
<select class="absolute top-52 right-10 z-20 rounded-xl px-2 py-1" bind:value={selected}>
    <option value="en-US">English-US</option>
    <option value="en-FR">French</option>
</select>