// 代码生成时间: 2025-10-14 17:47:55
import { ref, onMounted } from 'vue';

export default {
    name: 'WebContentScraper',
    setup() {
        const url = ref('');
        const content = ref('');
        const scrapeError = ref('');

        function scrapeContent() {
            scrapeError.value = '';
            fetch(url.value)
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Network response was not ok');
                    }
                    return response.text();
                })
                .then(html => {
                    content.value = html;
                })
                .catch(error => {
                    scrapeError.value = error.message;
                });
        }

        onMounted(() => {
            console.log('WebContentScraper component is mounted.');
        });

        return { url, content, scrapeError, scrapeContent };
    }
};
</script>

<style>
/* Add your styles here */
.error {
    color: red;
}
.content {
    white-space: pre-wrap;
}
</style>
