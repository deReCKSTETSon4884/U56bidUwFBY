// 代码生成时间: 2025-10-30 01:22:18
export default {
  name: 'IssueTrackingComponent',
  data() {
    return {
      newIssue: {
        title: '',
        description: ''
      },
      issues: []
    };
  },
  methods: {
    addIssue() {
      if (this.newIssue.title.trim() && this.newIssue.description.trim()) {
        this.issues.push({
          ...this.newIssue
        });
        this.newIssue.title = '';
        this.newIssue.description = '';
      } else {
        alert('标题和描述不能为空');
      }
    },
    removeIssue(index) {
      this.issues.splice(index, 1);
    }
  },
  mounted() {
    console.log('组件已挂载');
  },
  beforeUnmount() {
    console.log('组件即将卸载');
  }
};
</script>

<style scoped>
/* 在这里添加样式 */
</style>