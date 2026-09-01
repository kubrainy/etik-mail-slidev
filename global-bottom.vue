<template>
  <div class="bg-layer">
    <div class="blob blob1" />
    <div class="blob blob2" />
    <div class="blob blob3" />
    <div class="blob blob4" />
    <div class="blob blob5" />
  </div>
</template>

<style scoped>
.bg-layer {
  position: fixed;
  inset: 0;
  z-index: -1;
  overflow: hidden;
  pointer-events: none;
}

.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.18;
  will-change: transform;
}

.blob1 {
  width: 420px;
  height: 420px;
  background: #ec4899;
  top: -100px;
  left: -80px;
  animation: float1 22s ease-in-out infinite;
}

.blob2 {
  width: 500px;
  height: 500px;
  background: #7c3aed;
  bottom: -150px;
  right: -100px;
  animation: float2 26s ease-in-out infinite;
  animation-delay: -4s;
}

.blob3 {
  width: 350px;
  height: 350px;
  background: #4f46e5;
  top: 40%;
  right: 15%;
  animation: float3 30s ease-in-out infinite;
  animation-delay: -10s;
}

.blob4 {
  width: 280px;
  height: 280px;
  background: #db2777;
  bottom: 10%;
  left: 8%;
  animation: float4 24s ease-in-out infinite;
  animation-delay: -6s;
  opacity: 0.14;
}

.blob5 {
  width: 320px;
  height: 320px;
  background: #6d28d9;
  top: 8%;
  right: 35%;
  animation: float5 28s ease-in-out infinite;
  animation-delay: -14s;
  opacity: 0.13;
}

@keyframes float1 {
  0%, 100% { transform: translate(0, 0) rotate(0deg); }
  33% { transform: translate(60px, 40px) rotate(8deg); }
  66% { transform: translate(20px, 80px) rotate(-6deg); }
}

@keyframes float2 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  33% { transform: translate(-50px, -30px) scale(1.08); }
  66% { transform: translate(-80px, 20px) scale(0.95); }
}

@keyframes float3 {
  0%, 100% { transform: translate(0, 0) scale(1) rotate(0deg); }
  50% { transform: translate(-30px, 50px) scale(1.1) rotate(10deg); }
}

@keyframes float4 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(40px, -60px) scale(1.15); }
}

@keyframes float5 {
  0%, 100% { transform: translate(0, 0) rotate(0deg); }
  50% { transform: translate(-40px, 30px) rotate(-12deg); }
}
</style>