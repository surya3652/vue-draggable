<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col-5">
          <h4 class="mb-3">Draggable 1</h4>
          <!-- pull option to clone means that dragging an element out of this list will clone the element and not move it permanently out of the list.
             And setting put to false means we can’t drag new elements into this group. -->
          <draggable
            class="draggable-list"
            :list="list1"
            :group="{
              name: 'mygroup',
              pull: 'clone',
              put: false,
            }"
          >
            <div class="list-item" v-for="element in list1" :key="element">
              {{ element }}
            </div>
          </draggable>
        </div>

        <div class="col-5">
          <h4 class="mb-3">Draggable 2</h4>
          <draggable
            class="draggable-list"
            :list="list2"
            :group="{ name: 'mygroup' }"
          >
            <div class="list-item" v-for="element in list2" :key="element">
              {{ element }}
            </div>
          </draggable>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import draggable from "vuedraggable";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  components: {
    draggable,
  },
  data() {
    return {
      list1: ["ABC", "DEF", 3, 4],
      list2: ["GHI", "JKL", 7, 8],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
.hello {
  background-color: #42b983;
  width: auto;
  height: auto;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.draggable-list {
  background: linear-gradient(180deg, #32294d, #6b5e9a, #ab9bd8);
  color: #fff;
  border: 1px solid;
  border-radius: 10px;
  height: 30vh;
}
.list-item {
  margin: 10px;
  padding: 40px;
  cursor: pointer;
  font-size: 18px;
  border-radius: 5px;
  border: 2px solid black;
  background: linear-gradient(#32294d, #6b5e9a, #ab9bd8);
  display: inline-block;
}
</style>
