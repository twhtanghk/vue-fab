<template>
  <label :class="[ $parent.actionIconSize, 'material-icons' ]" @click.stop >
    <i :class="[ $parent.actionIconSize, 'material-icons' ]">{{action.icon}}</i>
    <input type='file' @change='change' multiple hidden />
  </label>
</template>

<script lang='coffee'>
export default
  props: [ 'action' ]
  methods:
    change: (event) ->
      @$parent.$emit @action.name,  event.target.files
      @$parent.toggle = false
</script>

<style lang='scss' scoped>
@import url(https://fonts.googleapis.com/icon?family=Material+Icons);

.fab-list li .material-icons {
  color: white;
}

label {
  cursor: inherit;
  margin: 0;
  i {
    vertical-align: middle;
    font-size: inherit;
  }
}

label.md-18 {
  height: 18px;
  width: 18px;
  font-size: 18px;
}

label.md-24 {
  height: 24px;
  width: 24px;
  font-size: 24px;
}

label.md-36 {
  height: 36px;
  width: 36px;
  font-size: 36px;
}

i.md-36.material-icons {
    left: 14px;
    right: 14px;
    top: 14px;
    bottom: 14px;
}
</style>
