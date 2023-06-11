<template>
    <div class="timeline">
      <div class="timeline-line"></div>
      <div v-for="(item, index) in timelineItems" :key="item.id" :class="['timeline-item', index % 2 === 0 ? 'higher' : 'lower']">
        <div class="timeline-item-content">
          <div class="timeline-item-image">
            <img :src="item.image" :alt="item.title" />
          </div>
          <div class="timeline-item-details">
            <h4 class="item-title">{{ item.title }}</h4>
            <p class="item-description">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        timelineItems: [
          {
            id: 1,
            title: 'Қонақтардың жиналуы',
            description: '18:30',
            image: 'https://thumb.tildacdn.com/tild6462-3365-4036-a234-653764623831/-/cover/200x200/center/center/-/format/webp/_WhatsApp_2023-05-16.jpg'
          },
          {
            id: 1,
            title: 'Беташар',
            description: '19:00',
            image: 'https://thumb.tildacdn.com/tild3232-6338-4438-b337-653065376633/-/cover/200x200/center/center/-/format/webp/_WhatsApp_2023-05-16.jpg'
          },
          {
            id: 2,
            title: 'Тойдың ашылу салтанаты',
            description: '20:00',
            image: 'https://thumb.tildacdn.com/tild3037-6430-4665-a138-333766316433/-/cover/200x200/center/center/-/format/webp/photo.jpg'
          },
          // Add more timeline items as needed
        ]
      };
    }
  };
  </script>
  
  <style>
  .timeline {
    position: relative;
  }
  .timeline-line {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 50%;
    width: 2px;
    background-color: #ccc;
    transform: translateX(-50%);
  }
  .timeline-item {
    font-family: Cormorant-600;
    position: relative;
    display: flex;
    align-items: center;
    margin-bottom: 20px;
  }
  .lower{
    justify-content: flex-end;
    margin-right: 1rem;
  }
  .higher{
    justify-content: flex-start;
    margin-left: 1rem;
  }
  .timeline-item.higher .timeline-item-content {
    /* align-items: flex-start; */
  }
  
  .timeline-item.lower .timeline-item-content {
    /* align-items: flex-end; */
  }
  
  .timeline-item-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px;
    background-color: #f0f0f0;
    border-radius: 8px;
    width: 40%;
  }
  
  .timeline-item-image img {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    object-fit: cover;
  }
  
  .timeline-item-details {
    margin-top: 10px;
    text-align: center;
  }
  
  .item-title {
    font-size: 16px;
    margin-bottom: 5px;
  }
  
  .item-description {
    font-size: 16px;
    margin-bottom: 0;
  }
  </style>
  
