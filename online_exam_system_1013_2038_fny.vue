// 代码生成时间: 2025-10-13 20:38:54
import { ref, reactive, computed, onMounted, onUnmounted } from 'vue';

const questions = ref([
    { text: 'Vue.js是什么？', options: ['A. 一本书', 'B. 一个框架', 'C. 一首歌', 'D. 一部电影'], correctAnswer: 'B' },
    // 更多的问题
]);

const selectedAnswer = ref('');
const currentQuestionIndex = ref(0);
const examState = ref('welcome');
const score = ref(0);

const currentQuestion = computed(() => questions.value[currentQuestionIndex.value]);

const submitAnswer = () => {
    if (selectedAnswer.value === currentQuestion.value.correctAnswer) {
        score.value++;
    }
    nextQuestion();
};

const nextQuestion = () => {
    if (currentQuestionIndex.value < questions.value.length - 1) {
        currentQuestionIndex.value++;
    } else {
        examState.value = 'results';
    }
};

const resetExam = () => {
    currentQuestionIndex.value = 0;
    selectedAnswer.value = '';
    score.value = 0;
    examState.value = 'welcome';
};

onMounted(() => {
    examState.value = 'question';
});

onUnmounted(() => {
    // 清理工作，如果有需要的话
});
</script>

<style scoped>
.online-exam-system {
    /* 样式内容 */
}
</style>