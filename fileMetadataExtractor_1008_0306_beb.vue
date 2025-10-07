// 代码生成时间: 2025-10-08 03:06:18
import { ref, onMounted, onUnmounted } from 'vue';

// Define reactive metadata data
const metadata = ref(null);

// Function to handle file change event
const handleFileChange = (event) => {
  const file = event.target.files[0];
  if (file) {
    metadata.value = {
      name: file.name,
      size: file.size,
      type: file.type,
      lastModified: new Date(file.lastModified).toLocaleString()
    };
  }
};

// Lifecycle hook to handle component setup
onMounted(() => {
  console.log('Component is mounted');
});

// Lifecycle hook to handle component cleanup
onUnmounted(() => {
  console.log('Component is unmounted');
});

</script>

<style scoped>
.file-metadata-extractor {
  margin: 20px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
