// 代码生成时间: 2025-09-23 18:51:08
import { ref, onMounted } from 'vue';

// 响应式数据
const files = ref([]);
const newFilename = ref('');
const renamedFiles = ref([]);

// 批量重命名逻辑
function renameFiles() {
    files.value.forEach(file => {
        const originalName = file.replace(/[\s\S]*\/, '');
        const newName = `${newFilename.value}${originalName}`;
        renamedFiles.value.push(newName);
    });
}

// 生命周期钩子：组件挂载时
onMounted(() => {
    // 可以在这里进行初始化或者其他挂载时需要执行的操作
    console.log('Component mounted');
});

</script>

<template>
    <div>
        <!-- 文件列表 -->
        <ul>
            <li v-for="file in files" :key="file">{{ file }}</li>
        </ul>

        <!-- 新文件名输入框 -->
        <input v-model="newFilename" placeholder="Enter new file name prefix"/>

        <!-- 批量重命名按钮 -->
        <button @click="renameFiles">Rename Files</button>

        <!-- 重命名结果列表 -->
        <ul v-if="renamedFiles.length > 0">
            <li v-for="renamedFile in renamedFiles" :key="renamedFile">{{ renamedFile }}</li>
        </ul>
    </div>
</template>

<style scoped>
/* 这里可以添加一些CSS样式 */
</style>
