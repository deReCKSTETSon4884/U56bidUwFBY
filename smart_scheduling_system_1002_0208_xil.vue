// 代码生成时间: 2025-10-02 02:08:31
import { ref, onMounted } from 'vue';

const courses = ref([]); // 响应式数据，存储课程信息

// 模拟从后端获取课程信息
const fetchCourses = () => {
  // 这里使用setTimeout模拟异步请求
  setTimeout(() => {
    courses.value = [
      { name: '数学', teacher: '张老师', time: '周一 8:00-9:00', classroom: 'A101' },
      { name: '物理', teacher: '李老师', time: '周二 10:00-11:00', classroom: 'A102' },
      { name: '化学', teacher: '王老师', time: '周三 14:00-15:00', classroom: 'A103' },
    ];
  }, 1000);
};

onMounted(fetchCourses); // 在组件挂载后获取课程信息
</script>

<style scoped>
.smart-scheduling-system table {
  width: 100%;
  border-collapse: collapse;
}
.smart-scheduling-system th, .smart-scheduling-system td {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: left;
}
.smart-scheduling-system th {
  background-color: #f2f2f2;
}
</style>