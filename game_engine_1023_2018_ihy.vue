// 代码生成时间: 2025-10-23 20:18:08
import { ref, onMounted, onUnmounted, reactive } from 'vue';

// 响应式数据
const gameCanvas = ref(null);
const gameContext = ref(null);
const gameData = reactive({
  playerPosition: { x: 0, y: 0 },
  enemyPosition: { x: 100, y: 100 }
});

// 生命周期钩子 - 组件挂载
onMounted(() => {
  initGame();
  animate();
});

// 生命周期钩子 - 组件卸载
onUnmounted(() => {
  cancelAnimationFrame(gameData.frameId);
});

// 初始化游戏
function initGame() {
  gameContext.value = gameCanvas.value.getContext('2d');
}

// 游戏动画循环
function animate() {
  gameData.frameId = requestAnimationFrame(animate);
  clearCanvas();
  drawPlayer();
  drawEnemy();
  handleClick();
}

// 清除画布
function clearCanvas() {
  gameContext.value.clearRect(0, 0, gameCanvas.value.width, gameCanvas.value.height);
}

// 绘制玩家
function drawPlayer() {
  gameContext.value.fillStyle = 'blue';
  gameContext.value.fillRect(gameData.playerPosition.x, gameData.playerPosition.y, 50, 50);
}

// 绘制敌人
function drawEnemy() {
  gameContext.value.fillStyle = 'red';
  gameContext.value.fillRect(gameData.enemyPosition.x, gameData.enemyPosition.y, 50, 50);
}

// 处理点击事件，移动玩家位置
function handleClick() {
  const rect = gameCanvas.value.getBoundingClientRect();
  const x = event.clientX - rect.left;
  const y = event.clientY - rect.top;
  gameData.playerPosition.x = x;
  gameData.playerPosition.y = y;
}
</script>

<style scoped>
.game-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.game-canvas {
  border: 1px solid black;
}
</style>