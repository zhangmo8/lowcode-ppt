---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
title: Lowcode
hideInToc: true
---

# Lowcode

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    快速查看 <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/varletjs/varlet-lowcode" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>


---
hideInToc: true
---

# Agenda

<Toc></Toc>


---
transition: fade-out
---


# Why this

- 为什么讲这个主题

- 为什么做这个平台


---
transition: slide-up
---

# 开源平台

| | |
| --- | --- |
| 平台名称 | 所属公司 | 
| <kbd>[宜搭](https://cn.aliyun.com/product/yida?from_alibabacloud=)</kbd> | 阿里 |
| <kbd>[formilyjs](https://formilyjs.org/)</kbd> | 阿里 |
| <kbd>[Astro Zero](https://www.huaweicloud.com/product/appcube.html)</kbd> | 华为 |
| <kbd>[通天塔](https://babel.m.jd.com/active/babelCommon/index.html#/)</kbd> | 京东 |
| <kbd>[无极](https://wujicode.cn/xy/app/prod/official/index)</kbd> | 腾讯 |

<div m-t-10px></div>

[更多其他平台](https://github.com/taowen/awesome-lowcode)

<style>
  .slidev-layout td, .slidev-layout th {
    padding-top:.5rem;
    padding-bottom: .5rem;
  }
</style>

---
transition: slide-up
layout: default
---

# Varlet lowcode

一个面向开发者的Vue Lowcode平台

<img src="/assets/designer.jpg" w-70vh m-auto />


---
transition: slide-up
hideInToc: true
---

## Monorepo

A monorepo is a `single repository` containing `multiple distinct projects`, with `well-defined relationships`.

```mermaid {theme: 'default', scale: 0.8}
graph TD
  A(Org) --- B(App 1)
  B --- G(...)
  B --- H(...)
  A --- C(Lib 1)
  A --- D(App 2)
  D --- I(...)
  A --- E(Lib 2)
  A --- F(Lib 4)
  style A fill:#F2C94C,stroke:#F2994A,stroke-width:2px
  style B fill:#B06AB3,stroke:#4568DC,stroke-width:2px
  style D fill:#B06AB3,stroke:#4568DC,stroke-width:2px
  style C fill:#6190E8,stroke:#A7BFE8,stroke-width:2px
  style E fill:#6190E8,stroke:#A7BFE8,stroke-width:2px
  style F fill:#6190E8,stroke:#A7BFE8,stroke-width:2px
  style G fill:#e96443,stroke:#093637,stroke-width:2px
  style H fill:#e96443,stroke:#093637,stroke-width:2px
  style I fill:#e96443,stroke:#093637,stroke-width:2px

```

对比：Monolithic / Multi-repo / Monorepo


1. Simplified code management (dependencies, configs...)
2. Improved code sharing


---
transition: slide-up
hideInToc: true
---

## Plugins

<div grid="~ cols-2 gap-4">
<div>

```js
function createPluginsManager() {
  const plugins = []

  const pluginsManager = {
    usePlugin
  }

  function usePlugin(plugin) {
    plugins.push(plugin)
    return pluginsManager
  }

  return pluginsManager
}
```

</div>
<div>

<Layout />

</div>
</div>


---
transition: slide-up
hideInToc: true
---

## Assets


---
transition: slide-up
hideInToc: true
---

## Schema

```js

const schema = (
  <page id={id()} code={code} css={css}>
    <node id={id()} library={'Varlet'} name={'Button'}>
      <t id={id()} textContent={'BUTTON 1'} />
    </node>
    <node id={id()} library={'Varlet'} name={'Button'}>
      <t id={id()} textContent={'BUTTON 2'} />
    </node>
  </page>
)

```
