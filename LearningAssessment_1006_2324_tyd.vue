// 代码生成时间: 2025-10-06 23:24:37
import { ref, reactive, computed, onMounted, onUnmounted } from 'vue';

// 响应式数据
const assessment = reactive({
  score: 0,
  grade: null,
});

// 计算属性，根据分数计算等级
const getGrade = computed(() => {
  if (assessment.score >= 90) return 'A';
  if (assessment.score >= 75) return 'B';
  if (assessment.score >= 60) return 'C';
  if (assessment.score >= 50) return 'D';
  return 'F';
});

// 生命周期钩子
onMounted(() => {
  console.log('组件已挂载');
  // 可以在这里执行组件初始化的操作
});

onUnmounted(() => {
  console.log('组件即将卸载');
  // 可以在这里执行清理操作
});

// 提交评估的方法
function submitAssessment() {
  console.log("提交的分数为: " + assessment.score + ", 等级为: " + getGrade.value);
  // 这里可以添加将数据发送到后端的逻辑
}
</script>

<style scoped>
/* 在这里添加你的样式 */
</style>
