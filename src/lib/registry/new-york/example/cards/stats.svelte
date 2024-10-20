<script lang="ts">
  import * as Card from '$lib/registry/new-york/ui/card/index.js';
  // import { Revenue, Subscription } from '$lib/components/docs/charts/index.js';

  let { details } = $props();
</script>

<a href={details.href} target="blank">
  <Card.Root>
    <!-- <Card.Header class="flex flex-row items-center justify-between space-y-0 pb-2">
			<Card.Title class="text-sm font-normal">Total Revenue</Card.Title>
		</Card.Header> -->
    <Card.Content>
      <div class="text-2xl font-bold">{details?.title}</div>
      <p class="text-xs text-muted-foreground">{details?.description}</p>
      <div class="h-[80px]">
        <!-- <Revenue /> -->
      </div>
    </Card.Content>
  </Card.Root>
</a>
