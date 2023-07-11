
---
transition: slide-left
---

# Core

聚合部分，全局的调度器


---
transition: slide-up
level: 2
---


# Schema

<div grid="~ cols-2 gap-4">
<div>

```ts {1-10|all}
interface SchemaNode {
  name: string;
  library?: string;
  id?: string;
  props?: SchemaNodeProps;
  slots?: SchemaNodeSlots;
  if?: SchemaNodeBinding;
  for?: SchemaNodeBinding;
  models?: string[];
}

interface SchemaPageNode extends SchemaNode {
  code?: string;
  css?: string;
  ...
}

...

```

</div>

<div>

```ts {1-10|12-21|all}
declare global {
  namespace JSX {
    interface IntrinsicElements {
      page: Exclude<SchemaPageNode, 'slots'>
      slot: { name?: string }
      node: Exclude<SchemaNode, 'slots'>
      t: Exclude<SchemaTextNode, 'slots'>
    }
  }
}

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

</div>

</div>

---
transition: slide-left
level: 2
---

# Assets

```ts {1-5|7-19|8|10-12|14-16|all}
interface Asset {
  profileLibrary?: string;
  profileResource?: string;
  additionResources?: string[];
}

function createAssetsManager() {
  function importAssets(assets) {}

  // css --> <link rel="stylesheet" href="..." /> 
  // js --> <script src="..." /> 
  function loadResources(resouce) {}

  // const Component = window.{libraryName}.{componentName}
  // h(Component, props, Slot)
  function findComponent(asstes, name, library) {}

  ...
}

```

---
transition: slide-up
level: 2
---

# Designer

Iframe 设计，方便路由设计，样式隔离


---
transition: slide-left
level: 2
---

# EventManager

事件派发

Core这个是需要单例

---
level: 2
---

# Plugins

<div grid="~ cols-2 gap-4">
<div>

```js {2|4-6|8-11|all}
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

