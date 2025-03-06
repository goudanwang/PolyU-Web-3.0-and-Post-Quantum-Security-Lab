<template>
    <div class="team-members">
      <div v-for="(member, index) in members" :key="index" class="member-card">
        <div class="member-photo">
          <img :src="member.photo" :alt="member.name" @error="handleImageError">
        </div>
        <div class="member-info">
          <h3 class="member-name">{{ member.name }}</h3>
          <p class="member-position">{{ member.position }}</p>
          <p class="member-bio">{{ member.bio }}</p>
          <p class="member-email">📧 {{ member.email }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue'
  
  const members = ref([])
  
  // 加载成员数据
  const fetchMembers = async () => {
    try {
      const response = await fetch('/data/members.json')
      members.value = await response.json()
    } catch (error) {
      console.error('加载成员数据失败:', error)
    }
  }
  
  // 图片加载失败处理
  const handleImageError = (event) => {
    event.target.src = '/images/placeholder.jpg' // 备用图片路径
  }
  
  onMounted(() => {
    fetchMembers()
  })
  </script>
  
  <style scoped>
  .team-members {
    max-width: 800px;
    margin: 0 auto;
  }
  
  .member-card {
    display: flex;
    gap: 2rem;
    margin-bottom: 2rem;
    padding: 1.5rem;
    background: #f8f9fa;
    border-radius: 8px;
  }
  
  .member-photo {
    flex: 0 0 160px; /* 设置宽度 */
  }
  
  .member-photo img {
    width: 160px; /* 调整宽度 */
    height: 256px; /* 调整高度，保持长方形比例 */
    object-fit: cover; /* 保持图像的比例 */
    border: 3px solid #e9ecef; 
  }
  
  .member-info {
    flex: 1;
  }
  
  .member-name {
    margin: 0 0 0.5rem;
    color: #2c3e50;
  }
  
  .member-position {
    margin: 0 0 1rem;
    color: #6c757d;
    font-weight: 500;
  }
  
  .member-bio {
    line-height: 1.6;
    color: #495057;
  }
  
  .member-email {
    margin: 1rem 0 0;
    color: #007bff;
  }
  </style>