<script>
  export let keywords = [];
  export let text = "";
  const highlight = (txt, tokens) => {
    let output = `${txt}`
    tokens.forEach((token) => {
      output = output.replace(new RegExp(`(${token})`,"gi"), "<span class=\"keyword-highlight\">$1</span>");
     });
    return output
  }
  $: highlightedText = highlight(text,keywords);
</script>
{@html highlightedText}
<style>
  :global(span.keyword-highlight) {
    background: var(--lighter-yellow);
    font-weight: inherit; }
</style>
