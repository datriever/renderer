<script lang='ts' module>
  import { marked } from 'marked'
  import type { MarkedRendererProps } from 'svelte-markdown'
  export type Props = MarkedRendererProps<marked.Tokens.Code>
  import type { Data, Layout } from 'svelte-plotly.js'

  export type Plot = {
    data: Data[],
    layout?: Partial<Layout>
  }

</script>

<script lang='ts'>
  import SvelteMarkdown from 'svelte-markdown';
  import Plotly from 'svelte-plotly.js';

  function parsePlot(json?: string): Plot {
    try {
      return JSON.parse(json!)
    } catch (e) {
      console.error('Parsing:', json, 'Error:', e)
      return { data: [] }
    }
  }

  const { text, lang, raw }: Props = $props()

</script>

{#if lang === 'plot'}
  {@const { data, layout } = parsePlot(text)}
  <Plotly {data} {layout} />
{:else}
  <SvelteMarkdown source={raw} />
{/if}
