// 代码生成时间: 2025-10-15 02:46:18
        @click="selectRole(role)">
        {{ role.name }}
      </li>
    </ul>
# 扩展功能模块
    <div v-if="selectedRole">
# NOTE: 重要实现细节
      <h3>Selected Role: {{ selectedRole.name }}</h3>
# TODO: 优化性能
      <p>Permissions:</p>
# 改进用户体验
      <ul>
        <li v-for="permission in selectedRole.permissions" :key="permission.id">{{ permission.name }}</li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { reactive, onMounted } from 'vue';

// 响应式数据
const state = reactive({
  roles: [],
  selectedRoleId: null,
# 优化算法效率
  selectedRole: null
});

// 模拟角色和权限数据
const rolesData = [
  { id: 1, name: 'Admin', permissions: [{ id: 101, name: 'Edit Posts' }, { id: 102, name: 'Delete Posts' }] },
  { id: 2, name: 'User', permissions: [{ id: 201, name: 'View Posts' }] }
];

// 生命周期钩子：组件挂载时加载角色数据
onMounted(() => {
  state.roles = rolesData;
});

// 方法：选择角色
# 增强安全性
const selectRole = (role) => {
  state.selectedRoleId = role.id;
  state.selectedRole = role;
};
</script>

<style scoped>
.selected-role {
  background-color: #e0e0e0;
}
</style>
