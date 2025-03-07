<template>
    <div class="latest-news">
      <h2 v-if="newsList.length">Latest News</h2>
      <ul class="news-list">
        <li v-for="(item, index) in sortedNews" :key="index" class="news-item">
          <div class="news-header">
            <span class="news-icon">{{ item.icon }}</span>
            <span class="news-date">{{ formatDate(item.date) }}</span>
          </div>
          <h3 class="news-title">{{ item.title }}</h3>
          <div class="news-meta">
            <span class="news-author">Author: {{ item.author }}</span>
          </div>
          <p class="news-details">{{ item.details }}</p>
        </li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref, computed, onMounted } from 'vue'
  
  const newsList = ref([])
  
  // 从 public 目录获取数据
  const fetchNews = async () => {
    try {
      const response = await fetch('/PolyU-Web-3.0-and-Post-Quantum-Security-Lab/data/news.json')
      newsList.value = await response.json()
    } catch (error) {
      console.error('Failed to load news:', error)
    }
  }
  
  // 处理日期格式
  const formatDate = (dateString) => {
    const date = new Date(dateString)
    return date.toLocaleDateString('en-US', {
      year: 'numeric',
      month: 'long',
      day: 'numeric'
    })
  }
  
  // 获取最新8条（按日期降序）
  const sortedNews = computed(() => {
    return [...newsList.value]
      .sort((a, b) => new Date(b.date) - new Date(a.date))
      .slice(0, 8)
  })
  
  onMounted(() => {
    fetchNews()
  })
  </script>
  
  <style scoped>
  .latest-news {
    margin: 2rem 0;
    border: 1px solid #eaecef;
    border-radius: 8px;
    padding: 1.5rem;
  }
  
  .news-list {
    list-style: none;
    padding: 0;
  }
  
  .news-item {
    margin-bottom: 2rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid #eee;
  }
  
  .news-item:last-child {
    border-bottom: none;
    margin-bottom: 0;
  }
  
  .news-header {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-bottom: 0.5rem;
  }
  
  .news-icon {
    font-size: 1.5em;
  }
  
  .news-date {
    color: #666;
    font-size: 0.9em;
  }
  
  .news-title {
    margin: 0.5rem 0;
    color: var(--c-brand);
  }
  
  .news-meta {
    font-size: 0.9em;
    color: #666;
    margin-bottom: 0.5rem;
  }
  
  .news-details {
    margin: 0;
    line-height: 1.6;
    color: #444;
  }
  </style>