<template>
  <div id="app">
    <div class="sql-box">
      <SqlEditor
        ref="sqleditor"
        :value="basicInfoForm.sqlMain"
        @changeTextarea="changeTextarea($event)"
      />
    </div>
    <el-button
        type="primary"
        size="small"
        class="sql-btn"
        @click="formaterSql(basicInfoForm.sqlMain)"
        >格式化sql</el-button
      >
  </div>
</template>

<script>
// import sqlFormatter from "./util/util";
import sqlFormatter from "sql-formatter";
import SqlEditor from "./components/SqlEditor";

export default {
  name: "app",
  components: {
    SqlEditor,
  },
  data() {
    return {
      basicInfoForm: {
        sqlMain: "",
      },
    };
  },
  methods: {
    changeTextarea(val) {
      this.$set(this.basicInfoForm, "sqlMain", val);
    },
    formaterSql(val) {
      let dom = this.$refs.sqleditor;
      dom.editor.setValue(sqlFormatter.format(dom.editor.getValue()));
    },
  },
};
</script>

<style>
#app {
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  align-items: flex-start;
  justify-items: center;
  flex-direction: column;
}
.sql-box{
  width:50%;
  border: 1px solid #ddd;
}
.sql-btn{
  margin-top: 20px;
}
</style>
