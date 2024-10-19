<script lang="ts">
  import { CardsStats } from './index.js';
</script>

<div class="md:grids-col-2 grid md:gap-4 lg:grid-cols-10 xl:grid-cols-11 xl:gap-4">
  <!-- 1st half -->
  <div class="space-y-4 lg:col-span-4 xl:col-span-6 xl:space-y-4">
    <CardsStats />
    <div class="grid gap-1 sm:grid-cols-[260px_1fr] md:hidden">
      <CardsStats />
      <div class="pt-3 sm:pl-2 sm:pt-0 xl:pl-4">
        <CardsStats />
      </div>
      <div class="pt-3 sm:col-span-2 xl:pt-4">
        <CardsStats />
      </div>
    </div>
    <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-1 xl:grid-cols-2">
      <div class="space-y-4 xl:space-y-4">
        <CardsStats />
        <CardsStats />
        <CardsStats />
      </div>
      <div class="space-y-4 xl:space-y-4">
        <CardsStats />
        <CardsStats />
        <div class="hidden xl:block">
          <CardsStats />
        </div>
      </div>
    </div>
  </div>

  <!-- 2nd half -->
  <div class="space-y-4 lg:col-span-6 xl:col-span-5 xl:space-y-4">
    <div class="hidden gap-1 sm:grid-cols-[260px_1fr] md:grid">
      <CardsStats />
      <div class="pt-3 sm:pl-2 sm:pt-0 xl:pl-3">
        <CardsStats />
      </div>
      <div class="pt-3 sm:col-span-2 xl:pt-3">
        <CardsStats />
      </div>
    </div>
    <div class="hidden md:block">
      <CardsStats />
    </div>
    <CardsStats />
    <div class="xl:hidden">
      <CardsStats />
    </div>
  </div>
</div>
