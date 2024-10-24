<script lang="ts">
  import { NavigationMenu } from 'bits-ui';
  import CaretDown from 'phosphor-svelte/lib/CaretDown';

  import { Icons } from '../icons/index.js';
  import { siteConfig } from '$lib/config/site.js';
  import { cn } from '$lib/utils.js';
  import { docsConfig } from '$lib/config/docs.js';
</script>

{#snippet ListItem({ className, title, content, href }: any)}
  <li>
    <NavigationMenu.Link
      target="_blank"
      class={cn(
        'block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-muted hover:text-accent-foreground focus:bg-muted focus:text-accent-foreground',
        className
      )}
      {href}
    >
      <div class="text-sm font-medium leading-none">{title}</div>
      <p class="line-clamp-2 text-sm leading-snug text-muted-foreground">
        {content}
      </p>
    </NavigationMenu.Link>
  </li>
{/snippet}

<div class="mr-4 hidden md:flex">
  <a href="/" class="mr-6 flex items-center space-x-2">
    <Icons.logo class="h-6 w-6" />
    <span class="hidden font-bold xl:inline-block">
      {siteConfig.name}
    </span>
  </a>
  <nav class="flex items-center gap-6 text-sm">
    <NavigationMenu.Root
      class="relative z-10 flex max-w-max flex-1 items-center justify-center"
    >
      <NavigationMenu.List
        class="group flex flex-1 list-none items-center justify-center space-x-1"
      >
        <NavigationMenu.Item>
          <NavigationMenu.Trigger
            class="group inline-flex h-10 w-max items-center justify-center rounded-md bg-background px-4 py-2 text-sm font-medium transition-colors hover:bg-muted hover:text-accent-foreground focus:bg-muted focus:text-accent-foreground focus:outline-none disabled:pointer-events-none disabled:opacity-50 data-[active]:bg-muted/50 data-[state=open]:bg-muted/50"
          >
            Stuff
            <CaretDown
              class="group-data[state=open]:rotate-180 relative top-[1px] ml-1 size-3 transition duration-200"
              aria-hidden="true"
            />
          </NavigationMenu.Trigger>
          <NavigationMenu.Content
            class="data-[motion^=from-]:animate-in data-[motion^=to-]:animate-out data-[motion^=from-]:fade-in data-[motion^=to-]:fade-out data-[motion=from-end]:slide-in-from-right-52 data-[motion=from-start]:slide-in-from-left-52 data-[motion=to-end]:slide-out-to-right-52 data-[motion=to-start]:slide-out-to-left-52 left-0 top-0 z-50 w-full md:absolute md:w-auto"
          >
            <ul
              class="grid w-[400px] gap-3 p-6 md:w-[500px] md:grid-cols-2 lg:w-[600px]"
            >
              {#each docsConfig.mainNav as component (component.title)}
                {@render ListItem({
                  href: component.href,
                  title: component.title,
                  content: component.description
                })}
              {/each}
            </ul>
          </NavigationMenu.Content>
        </NavigationMenu.Item>

        <!-- Blog -->
        <NavigationMenu.Item>
          <NavigationMenu.Link
            class="group inline-flex h-10 w-max items-center justify-center rounded-md bg-background px-4 py-2 text-sm font-medium transition-colors hover:bg-muted hover:text-accent-foreground focus:bg-muted focus:text-accent-foreground focus:outline-none disabled:pointer-events-none disabled:opacity-50 data-[active]:bg-muted/50 data-[state=open]:bg-muted/50"
            href="https://blog.buildersofstuff.com"
            target="_blank"
          >
            Blog
          </NavigationMenu.Link>
        </NavigationMenu.Item>

        <NavigationMenu.Indicator
          class="data-[state=visible]:animate-in data-[state=hidden]:animate-out data-[state=hidden]:fade-out data-[state=visible]:fade-in top-full z-[1] flex h-1.5 items-end justify-center overflow-hidden"
        >
          <div
            class="relative top-[60%] size-2 rotate-45 rounded-tl-sm bg-border shadow-md"
          ></div>
        </NavigationMenu.Indicator>
      </NavigationMenu.List>
      <div class="absolute left-0 top-full flex justify-center">
        <NavigationMenu.Viewport
          class="origin-top-center data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-90 relative mt-1.5 h-[var(--bits-navigation-menu-viewport-height)] w-full overflow-hidden rounded-md border bg-background text-popover-foreground shadow-lg md:w-[var(--bits-navigation-menu-viewport-width)]"
        />
      </div>
    </NavigationMenu.Root>

    <!-- <a
      href="/docs/components"
      class={cn(
        'transition-colors hover:text-foreground/80',
        $page.url.pathname.startsWith('/docs/components')
          ? 'text-foreground'
          : 'text-foreground/60'
      )}
    >
      Components
    </a>
    <a
      href="/themes"
      class={cn(
        'transition-colors hover:text-foreground/80',
        $page.url.pathname.startsWith('/themes')
          ? 'text-foreground'
          : 'text-foreground/60'
      )}
    >
      Themes
    </a>
    <a
      href="/examples"
      class={cn(
        'transition-colors hover:text-foreground/80',
        $page.url.pathname.startsWith('/examples')
          ? 'text-foreground'
          : 'text-foreground/60'
      )}
    >
      Examples
    </a>

    <a
      href="/blocks"
      class={cn(
        'transition-colors hover:text-foreground/80',
        $page.url.pathname.startsWith('/blocks')
          ? 'text-foreground'
          : 'text-foreground/60'
      )}
    >
      Blocks
    </a>
    <a
      href="/colors"
      class={cn(
        'transition-colors hover:text-foreground/80',
        $page.url.pathname.startsWith('/colors')
          ? 'text-foreground'
          : 'text-foreground/60'
      )}
    >
      Colors
    </a> -->
  </nav>
</div>
