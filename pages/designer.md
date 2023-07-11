---
transition: slide-left
---

# Designer

渲染设计器

```ts

eventsManager.on(BuiltInEvents.SCHEMA_CHANGE, async (newSchema) => {
  // re mountRenderer
})
// ... other event: Resize, CSS inject


function initIframe() {
  // ...init 
  iframeElement = container.value!.querySelector('iframe')

  if (iframeElement) {
    container.value!.removeChild(iframeElement)
  }

  iframeElement = document.createElement('iframe')
  container.value!.appendChild(iframeElement)
  iframeElement.contentWindow!.name = 'rendererWindow'
}

async function mountRenderer() {
  // ...initIframe...
  initIframe()

  // ...Mount Iframe & Inject CSS

  // ... init Renderer ...
  renderer = iframeWindow.VarletLowcodeRenderer.default
  renderer.schema.value = schema
  // ...other Attrs Inject
  renderer.init({ mountRoot: '#app', designerEventsManager: eventsManager })
  renderer.mount()
}


// Renderer
function renderSchemaNode(schemaNode: SchemaNode, scopeVariables: ScopeVariables): VNode {
  if (!schemaNode.hasOwnProperty('for')) {
    return withDesigner(schemaNode, scopeVariables)
  }

  // ... some vue template

  return h(
    Fragment,
    null,
    renderList(bindingValue, (item, index) => {
      const clonedSchemaNode = schemaManager.cloneSchemaNode(schemaNode)

      return withDesigner(
        clonedSchemaNode,
        createNewScopeVariables(scopeVariables, {
          id: `item${schemaNode.id}`,
          $item: {
            ...scopeVariables.$item,
            [schemaNode.id!]: item,
          },
          $index: {
            ...scopeVariables.$index,
            [schemaNode.id!]: index,
          },
        })
      )
    })
  )
}
```

<style>
  .slidev-code-wrapper  {
    height: 400px;
    overflow: auto;
  }
</style>

