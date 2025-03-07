<!-- .vuepress/components/SimpleNews.vue -->
<template>
    <div class="simple-news">
      <div 
        v-for="(item, index) in sortedNews" 
        :key="index"
        class="news-item"
      >
        <p class="news-content">
          {{ item.icon }} {{ formatYearMonth(item.date) }}: {{ item.title }}
        </p>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, computed, onMounted } from 'vue'
  
  const newsList = ref([])
  
  const fetchNews = async () => {
    try {
      const response = await fetch('/PolyU-Web-3.0-and-Post-Quantum-Security-Lab/data/news.json')
      newsList.value = await response.json()
    } catch (error) {
      console.error('Failed to load news:', error)
    }
  }
  
  const formatYearMonth = (dateString) => {
    const date = new Date(dateString)
    return date.toLocaleDateString('en-US', {
      year: 'numeric',
      month: 'numeric'
    }).replace('/', '-')
  }
  
  const sortedNews = computed(() => {
    return [...newsList.value]
      .sort((a, b) => new Date(b.date) - new Date(a.date))
      .slice(0, 5)
  })
  
  onMounted(() => {
    fetchNews()
  })
  </script>
  
  <style scoped>
  .simple-news {
    width: 700px;
    margin: 0 auto;
    margin-bottom: 20px;
    text-align: center;
  }
  
  .news-item {
    padding: 8px 0;
  }
  
  .news-content {
    margin: 0;
    font-size: 16px;
    line-height: 1.6;
    color: #333;
  }
  </style>
  