<template>
  <div border-rd border-1 p-1 mr-1>
    <header flex border-rd border-1 px-2 py-1 justify-between m-1>
      <div>Header Left</div>
      <div>Header Center</div>
      <div>Header Right</div>
    </header>
    <main border-rd border-1 p-1 flex m-1 h-xs>
      <div border-rd border-1 border-dashed m-1 p-1 flex flex-col justify-between>
        <div>Sidebar Top</div>
        <div>Sidebar Bottom</div>
      </div>
      <div w-xl border-rd border-1 border-dashed m-1 p-1 text-center>Designer</div>
      <div flex-1 border-rd border-1 border-dashed m-1 p-1 text-center>Setters</div>
    </main>
  </div>
</template>