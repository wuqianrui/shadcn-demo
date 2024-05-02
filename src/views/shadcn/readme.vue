<template>
  <!-- main layout -->
  <div class="flex min-h-screen flex-col bg-background" id="application">
    <!-- header -->
    <header class="sticky top-0 z-40 border-b border-border bg-background bg-orange-300">
      header
    </header>
    <!-- header -->
    <!-- main content -->
    <main class="flex-1">
      <div class="flex w-full max-w-[88rem] mx-auto px-4 gap-10">
        <!-- content: left navigation -->
        <div
          class="fixed top-14 z-30 -ml-2 hidden h-[calc(100vh-3.5rem)] w-64 shrink-0 md:sticky md:block"
        >
          <ScrollArea class="py-6 h-full pr-6 lg:py-8">
            <div class="w-full">
              <div class="pb-4">
                <h4 class="mb-1 rounded-md py-1 text-sm font-semibold text-foreground">
                  Navition Title
                </h4>

                <div
                  class="grid grid-flow-row auto-rows-max text-sm"
                  v-for="doc in docs"
                  v-bind:key="doc.name"
                >
                  <RouterLink
                    :to="doc.href"
                    class="text-muted-foreground hover:underline py-1.5 font-medium transition-colors"
                    :class="{
                      '!font-semibold !text-foreground': $route.path === doc.href
                    }"
                  >
                    {{ doc.name }}
                  </RouterLink>
                </div>
              </div>

              <div class="pb-4">
                <h4 class="mb-1 rounded-md py-1 text-sm font-semibold text-foreground">
                  Components
                </h4>

                <div
                  class="grid grid-flow-row auto-rows-max text-sm text-muted-foreground hover:underline py-1.5 font-medium transition-colors"
                  v-for="tab in tabList"
                  :key="tab"
                >
                  {{ tab }}
                </div>
              </div>
            </div>
          </ScrollArea>
        </div>
        <!-- content: left navigation -->
        <!-- content: main content layout -->
        <main class="relative flex-grow py-6 lg:gap-10 lg:py-7 w-full max-w-3xl">
          <!-- fulltext - navigation -->
          <ol class="flex items-center whitespace-nowrap min-w-0">
            <!-- li 01 -->
            <li class="text-sm text-muted-foreground">
              <component
                :is="`span`"
                class="flex items-center"
                :class="{
                  '!font-semibold !text-foreground': false
                }"
              >
                <!-- 导航栏标题 -->
                Docs
                <!-- 标题导航栏 箭头  Doc > Compent -->
                <ChevronRight class="flex-shrink-0 h-3 w-3 text-muted-foreground mx-2" />
              </component>
            </li>
            <!-- li 01 -->
            <!-- li 02 -->
            <li class="text-sm text-muted-foreground">
              <component :is="`span`" class="flex items-center !font-semibold !text-foreground">
                <!-- 导航栏标题 -->
                Title
                <!-- 标题导航栏 箭头  Doc > Compent -->
                <ChevronRight class="flex-shrink-0 h-3 w-3 text-muted-foreground mx-2" />
              </component>
            </li>

            <!-- li 02 -->
          </ol>
          <!-- fulltext - navigation -->
          <!-- fulltext - title -->
          <div class="grid space-y-1 pt-6">
            <h1 class="text-4xl font-heading text-foreground">Blog Title</h1>
            <p class="text-muted-foreground text-lg max-w-xl">
              描述文章内容的句子，这里会做一个大致的介绍，以及简介。所以可以通过这里进行快速的了解
            </p>
          </div>
          <!-- fulltext - title -->

          <!-- fulltext - badge list -->
          <div class="flex space-x-4 pt-4">
            <Badge variant="default" class="cursor-pointer">
              <TablerBrandRadixUi class="w-3 h-3 mr-1" />
              Radix UI
            </Badge>

            <!-- badge02 -->
            <Badge variant="destructive" class="cursor-pointer">
              <TablerBrandRadixUi class="w-3 h-3 mr-1" />
              destructive
            </Badge>
            <!-- badge02 -->

            <Badge variant="secondary" class="cursor-pointer">
              <TablerBrandRadixUi class="w-3 h-3 mr-1" />
              secondary
            </Badge>

            <Badge variant="outline" class="cursor-pointer">
              <TablerBrandRadixUi class="w-3 h-3 mr-1" />
              outline
            </Badge>

            <Badge variant="success" class="cursor-pointer">
              <TablerBrandRadixUi class="w-3 h-3 mr-1" />
              success
            </Badge>
          </div>
          <!-- fulltext - badge list -->

          <!-- fulltext icon config -->
          <div class="pt-8">
            <h1 class="text-2xl font-heading text-foreground">
              Icon <SvgLoadingIcon class="inline-block" />
            </h1>
            <Separator class="mt-4 mb-6" />
            <component
              :is="`a`"
              href="https://icon-sets.iconify.design/?category=General&query=radix"
              target="_blank"
              class="text-foreground hover:underline"
              >Iconify config</component
            >
          </div>
          <!-- fulltext icon config -->

          <!-- fulltext - desc -->
          <div class="pt-8">
            <h1 class="text-2xl font-heading text-foreground">Shadcn</h1>
            <Separator class="mt-4 mb-6" />
            <blockquote class="mt-6 border-l-2 pl-6 italic">"收集 Shadcn 没有的组件"</blockquote>

            <ul class="my-6 ml-6 list-disc [&>li]:mt-2">
              <!-- docs -->
              <li>时间选择器，hms 格式 - 时分秒</li>
            </ul>
          </div>
          <!-- fulltext - desc -->

          <!-- fulltext - docs -->
          <div class="pt-8">
            <h1 class="text-2xl font-heading text-foreground">Docs</h1>
            <Separator class="mt-4 mb-6" />
            <ul class="my-6 ml-6 list-disc [&>li]:mt-2">
              <!-- docs -->
              <li>
                <component
                  :is="`a`"
                  href="https://ui.shadcn.com/docs/components/typography"
                  target="_blank"
                  class="text-foreground hover:underline"
                >
                  <h2 class="text-base">
                    <TablerBrandRadixUi class="inline-block" /> shadcn typography
                  </h2>
                </component>
              </li>
              <p class="text-muted-foreground text-sm mt-2">
                shadcn-ui 文档格式示例，可以直接在上面复制样式。
              </p>
              <!-- docs -->
              <!-- docs -->
              <li>
                <component
                  :is="`a`"
                  href="https://tailwindcss.com/docs/font-size"
                  target="_blank"
                  class="text-foreground hover:underline"
                >
                  <h2 class="text-base">
                    <TablerBrandRadixUi class="inline-block" /> tailwind css
                  </h2>
                </component>
              </li>
              <p class="text-muted-foreground text-sm mt-2">tailwind css 样式快速查询</p>
              <!-- docs -->
              <!-- docs -->
              <li>
                <component
                  :is="`a`"
                  href="https://play.tailwindcss.com/"
                  target="_blank"
                  class="text-foreground hover:underline"
                >
                  <h2 class="text-base">
                    <TablerBrandRadixUi class="inline-block" /> tailwind play 
                  </h2>
                </component>
              </li>
              <p class="text-muted-foreground text-sm mt-2">tailwind css 在线调试</p>
              <!-- docs -->
            </ul>
          </div>
          <!-- fulltext - docs -->
          <!-- fulltext - github repo -->
          <div class="pt-8">
            <h1 class="text-2xl font-heading text-foreground">Github Repo</h1>
            <Separator class="mt-4 mb-6" />
            <ul class="my-6 ml-6 list-disc [&>li]:mt-2">
              <li>
                <component
                  :is="`a`"
                  href="https://github.com/faturputro/vue-shadcn-dashboard"
                  target="_blank"
                  class="text-foreground hover:underline"
                >
                  <h2 class="text-base"><Github class="inline-block" /> vue-shadcn-dashboard</h2>
                </component>
              </li>
              <p class="text-muted-foreground text-sm mt-2">
                shadcn-vue 的后台面板模版项目，内置引入了大部分的组件。后续项目主要以这个为主。
              </p>
              <!-- github repo -->
              <!-- github repo -->
              <li>
                <component
                  :is="`a`"
                  href="https://github.com/ahmedmayara/shadcn-vue"
                  target="_blank"
                  class="text-foreground hover:underline"
                >
                  <h2 class="text-base"><Github class="inline-block" /> shadcn-vue</h2>
                </component>
              </li>
              <p class="text-muted-foreground text-sm mt-2">
                shadcn-vue 拥有部分组件，且有着官方文档的示例。
              </p>
              <!-- github repo -->
            </ul>
          </div>
          <!-- fulltext - github repo -->
        </main>
        <!-- content: main content layout -->
      </div>
    </main>
    <!-- main content -->
    <!-- footer -->
    <footer class="z-40 border-t border-border bg-background text-foreground">footer</footer>
    <!-- footer -->
  </div>
  <!-- main layout -->
</template>

<script setup lang="ts">
/* 引入图标 */
import { TablerBrandRadixUi, SvgLoadingIcon, Github } from '@/components/icon'
import { ScrollArea } from '@/components/ui/scroll-area'
import { Separator } from '@/components/ui/separator'
import { Badge } from '@/components/ui/badge'
import { ChevronRight } from 'lucide-vue-next'

interface Documentation {
  name: string
  href: string
}

const tabList = [
  'tab01',
  'tab02',
  'tab03',
  'tab04',
  'tab05',
  'tab06',
  'tab07',
  'tab08',
  'tab09',
  'tab10',
  'tab11',
  'tab12',
  'tab13',
  'tab14',
  'tab15',
  'tab16',
  'tab17',
  'tab18',
  'tab19',
  'tab20',
  'tab21',
  'tab22',
  'tab23',
  'tab24',
  'tab25',
  'tab26',
  'tab27',
  'tab28',
  'tab29',
  'tab30'
]

const docs: Documentation[] = [
  {
    name: 'Introduction',
    href: '/docs'
  },
  {
    name: 'Installation',
    href: '/docs/installation'
  },
  {
    name: 'Theming',
    href: '/docs/theming'
  },
  {
    name: 'Dark Mode',
    href: '/docs/dark-mode'
  },
  {
    name: 'CLI',
    href: '/docs/cli'
  },
  {
    name: 'About',
    href: '/docs/about'
  }
]
</script>

<style></style>
