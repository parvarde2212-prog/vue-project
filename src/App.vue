
<template>
  <div class="counter-page" dir="rtl">
    <div class="counter-card">

      <div class="icon">🍊</div>

      <h1>شمارنده من</h1>
      <p class="subtitle">هر عدد، یک قدم رو به جلو!</p>

      <div class="counter-circle">
        <span class="count">
          {{ count.toLocaleString('fa-IR') }}
        </span>
        <span class="count-label">تعداد شمارش</span>
      </div>

      <div class="buttons">
        <button class="btn increase" @click="count++">
          <span>＋</span>
          افزایش
        </button>

        <button
          class="btn decrease"
          @click="count > 0 && count--"
          :disabled="count === 0"
        >
          <span>－</span>
          کاهش
        </button>
      </div>

      <button class="reset-btn" @click="count = 0">
        ↻ بازنشانی شمارنده
      </button>

      <div class="footer">
        ساخته شده با 🧡
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<style scoped>
.counter-page {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #fff7ed, #ffedd5);
  font-family: Tahoma, sans-serif;
  padding: 20px;
}

.counter-card {
  width: 100%;
  max-width: 380px;
  background: #ffffff;
  border-radius: 28px;
  padding: 35px 25px;
  text-align: center;
  box-shadow: 0 15px 45px rgba(234, 88, 12, 0.12);
  border: 1px solid #ffedd5;
}

.icon {
  width: 75px;
  height: 75px;
  background: #ffedd5;
  border-radius: 22px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 38px;
  margin: 0 auto 18px;
}

h1 {
  color: #9a3412;
  font-size: 26px;
  margin: 0 0 10px;
}

.subtitle {
  color: #a8a29e;
  font-size: 13px;
  margin-bottom: 30px;
}

.counter-circle {
  width: 190px;
  height: 190px;
  border-radius: 50%;
  background: linear-gradient(145deg, #fff7ed, #fed7aa);
  border: 5px solid #fdba74;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0 auto 30px;
  box-shadow: 0 8px 25px rgba(249, 115, 22, 0.12);
}

.count {
  font-size: 48px;
  font-weight: bold;
  color: #ea580c;
}

.count-label {
  color: #9a3412;
  font-size: 13px;
  margin-top: 5px;
}

.buttons {
  display: flex;
  gap: 12px;
  justify-content: center;
}

.btn {
  flex: 1;
  padding: 14px 10px;
  border: none;
  border-radius: 14px;
  font-size: 15px;
  font-weight: bold;
  cursor: pointer;
  transition: 0.2s;
}

.increase {
  background: #f97316;
  color: white;
}

.decrease {
  background: #ffedd5;
  color: #c2410c;
}

.btn:hover:not(:disabled) {
  transform: translateY(-3px);
  filter: brightness(0.96);
}

.btn:disabled {
  opacity: 0.45;
  cursor: not-allowed;
}

.reset-btn {
  margin-top: 18px;
  background: transparent;
  border: none;
  color: #ea580c;
  font-size: 13px;
  cursor: pointer;
  padding: 10px;
}

.reset-btn:hover {
  color: #9a3412;
}

.footer {
  margin-top: 25px;
  color: #c4a18a;
  font-size: 12px;
}
</style>
