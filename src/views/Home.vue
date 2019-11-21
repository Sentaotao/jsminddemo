<template>
  <div class="home">
    <h1>123456</h1>
    <div id="jsmind_container"></div>
    <h2>654321</h2>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  mounted() {
    var options = {
      container: "jsmind_container",
      theme: "greensea",
      editable: true,
      mode :'full', 
      //是否垂直显示
      // displayVertical: false,
      displayVertical: true,
      //是否使用折线
      brokenLine: true,
      view: {
        hmargin: 100,
        vmargin: 50,
        line_width: 2,
        line_color: "#555"
      },
      layout: {
        hspace: 30,
        vspace: 100,
        pspace: 13
      },
      default_event_handle: {
        enable_mousedown_handle: true,
        enable_click_handle: true,
        enable_dblclick_handle: true
      },
      shortcut: {
        enable: true,
        handles: {},
        mapping: {
          addchild: 45, // Insert
          addbrother: 13, // Enter
          editnode: 113, // F2
          delnode: 46, // Delete
          toggle: 32, // Space
          left: 37, // Left
          up: 38, // Up
          right: 39, // Right
          down: 40 // Down
        }
      }
    };
    var mind = {
      /* 元数据，定义思维导图的名称、作者、版本等信息 */
      meta: {
        name: "jsMind-demo-tree",
        author: "hizzgdev@163.com",
        version: "0.2"
      },
      /* 数据格式声明 */
      format: "node_tree",
      /* 数据内容 */
      data: {
        id: "root",
        topic: "jsMind",
        children: [
          {
            id: "easy",
            topic: "Easy",
            direction: "left",
            expanded: false,
            children: [
              { id: "easy1", topic: "Easy to show" },
              { id: "easy2", topic: "Easy to edit" },
              { id: "easy3", topic: "Easy to store" },
              { id: "easy4", topic: "Easy to embed" }
            ]
          },
          {
            id: "open",
            topic: "Open Source",
            direction: "left",
            expanded: true,
            children: [
              { id: "open1", topic: "on GitHub" },
              { id: "open2", topic: "BSD License" }
            ]
          },
          {
            id: "powerful",
            topic: "Powerful",
            direction: "left",
            children: [
              { id: "powerful1", topic: "Base on Javascript" },
              { id: "powerful2", topic: "Base on HTML5" },
              { id: "powerful3", topic: "Depends on you" }
            ]
          },
          {
            id: "other",
            topic: "test node",
            direction: "left",
            children: [
              { id: "other1", topic: "I'm from local variable" },
              { id: "other2", topic: "I can do everything" }
            ]
          }
        ]
      }
    };
    var jm = new jsMind(options);
    jm.show(mind);
  }
};
</script>
<style lang="stylus">
body, html, #jsmind_container {
  width: 1000px;
  height: 800px;
}
</style>