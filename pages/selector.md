---
transition: slide-up
---

# Selector

元素选择器

<div grid="~ cols-2 gap-4" items-center>

<div>

```ts
// base/default style
const initStyle: CSSProperties = {...}

function computedSelectorStyles(id: string) {
  const node = document.querySelectorAll(`#item${id}`)
  
  const { top, left, width, height } = node.getBoundingClientRect()
  // get Rect Info
  const _style: CSSProperties = {
    top: `${top}px`,
    left: `${left}px`,
    width: `${width}px`,
    height: `${height}px`,
  }
  // merge custom style
  return { ..._style, ...initStyle }
}

// dispatch click event
function handleClick(event: Event) {}
```

</div>
<div>

```tsx
<template>
  <div key={Symbol(style.toString())} style={style}>
    <PluginRender {...props} />
  </div>
</template>

const builtInPlugins: SelectorPlugin[] = [
  {
    name: 'remove',
    component: Remove,
  },
]

const PluginRender = (props) => (
   const { plugins } = props
   <div class="varlet-low-code-selector__plugins">
      {plugins.map((plugin: SelectorPlugin) => {
        const PluginComponent = plugin.component as DefineComponent
        return <PluginComponent {...props} />
      })}
    </div>
)
```

</div>

</div>

<style>
  .slidev-code-wrapper  {
    height: 400px;
    overflow: auto;
  }
</style>
