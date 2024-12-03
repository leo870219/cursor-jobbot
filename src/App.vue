<script setup>
import { ref } from 'vue'
import 'uno.css'

const messages = ref([
  {
    type: 'bot',
    content: '九九你好，我是 104 AI JobBot，你專屬的推薦工作機器人。透過和你的互動，我將持續學習並了解你的求職偏好，並且根據這些資資直推薦最適合你的工作機會。',
    time: new Date()
  }
])

const options = [
  {
    title: '提供求職條件',
    description: '明確告訴機器人你的求職條件，可以獲得準確的求職推薦訊息'
  },
  {
    title: '學了解互動',
    description: '了解怎麼跟機器人互動的詳細說明'
  }
]
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <header class="h-16 bg-white border-b border-gray-200 flex items-center px-4">
      <img src="/104-logo.png" alt="104" class="h-8">
      <span class="ml-2 text-xl font-bold">人力銀行</span>
    </header>

    <main class="max-w-4xl mx-auto p-4">
      <div class="bg-white rounded-lg shadow p-6">
        <div class="flex items-center mb-4">
          <h1 class="text-xl font-bold">104 AI JobBot</h1>
          <span class="ml-2 px-2 py-0.5 bg-orange-100 text-orange-600 rounded text-sm">Beta</span>
        </div>

        <div class="space-y-4">
          <div v-for="(message, index) in messages" :key="index" 
               class="flex items-start gap-3">
            <div class="w-8 h-8 rounded-full bg-orange-500 flex items-center justify-center text-white">
              AI
            </div>
            <div class="flex-1">
              <div class="bg-gray-100 rounded-lg p-4">
                {{ message.content }}
              </div>
              <div class="text-sm text-gray-500 mt-1">
                {{ message.time.toLocaleTimeString() }}
              </div>
            </div>
          </div>
        </div>

        <div class="mt-8 grid grid-cols-2 gap-4">
          <div v-for="(option, index) in options" :key="index"
               class="bg-orange-50 rounded-lg p-4 cursor-pointer hover:bg-orange-100 transition-colors">
            <h3 class="font-bold text-orange-600">{{ option.title }}</h3>
            <p class="text-sm text-gray-600 mt-2">{{ option.description }}</p>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style>
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
}
</style>
