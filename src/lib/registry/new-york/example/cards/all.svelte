<script lang="ts">
  import { docsConfig } from '$lib/config/docs.js';
  import { CardsStats } from './index.js';
</script>

<div class="md:grids-col-2 grid gap-4 lg:grid-cols-4">
  {#each docsConfig.mainNav as details (details.title)}
    <CardsStats {details} />
  {/each}
</div>
