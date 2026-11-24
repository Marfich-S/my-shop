<template>
  <table>
    <thead>
      <tr>
        <th>Name</th>
        <th>Rating</th>
        <th>Comment</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(review, index) in reviews" :key="index">
        <td>{{ review.Name }}</td>
        <td>{{ review.Rating }}</td>
        <td>{{ review.Comment }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import Papa from 'papaparse';

export default {
  data() {
    return {
      reviews: [],
    };
  },
  created() {
    const csvContent = `
Name,Rating,Comment
Іван,5,Дякую за швидку доставку
Ольга,5,Все супер! Буду замовляти ще
Андрій,5,"Обслуговування, як завжди - на висоті"
Марина,4,"Все чудово! Покупкою задоволена, але коробка була прим'ята."
Сергій,5,Рекомендую цей чудовий магазин усім!
Данило,5,Дуже демократичні ціни. Я завжди купую лише тут.
Матвій,5,Дякую за подарунок до покупки - завжди радуєте приємними сюрпризами.
Анна,5,Дякую за чудові знижки
Раймонд,4,"Як завжди все кльово, але малий термін гарантії для годинника, хотілося б довше."
    `;

    Papa.parse(csvContent.trim(), {
      header: true,
      skipEmptyLines: true,
      complete: (result) => {
        this.reviews = result.data;
      },
    });
  },
};
</script>

<style scoped>
table {
  width: 90%;
  margin: 30px auto;
}
th, td {
  background: #f8f9fa;
  padding: 4px;
}
</style>
