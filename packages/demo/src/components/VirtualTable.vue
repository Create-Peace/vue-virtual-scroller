<template>
  <div class="virtual-table">
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <div>1</div>
    <RecycleScroller
          ref="scroller"
          class="scroller"
          :items="items"
          listTag="table"
          bodyTag="tbody"
          key-field="_id"
          item-tag="tr"
          size-field="height"
          :item-size="20"
          :buffer="buffer"
          :key="true"
          page-mode
        >
        <template slot-scope="props">
        <thead v-if="props.itemIndex === 0">
          <tr>
            <td>Age</td>
            <td>Name</td>
            <td>Company</td>
          </tr>
        </thead>
      
        <template>
          <td>{{props.itemIndex}}</td>
          <td>{{props.item.name}}</td>
          <td>{{props.item.company}}</td>
        </template>
      </template>
        </RecycleScroller>
  </div>
</template>
<script>
import items from "./data.json";

export default { 
  name: 'VirtualTable',
  data () {
    return {
      items
    }
  }
}
</script>