<template>
  <v-container>
    <v-card dir="rtl">
      <v-card-title>
        <p  class="tab">
          {{ title }}
        </p>
      </v-card-title>
      <v-card-subtitle>
        <p  class="tab">
          {{ subtitle }}
        </p>
      </v-card-subtitle>
      <v-card-text>
        <p class="pre-formatted">
          {{ text }}
        </p>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: "AboutMe",
  data: () => ({
    title: 'שלום, קוראים לי אחיה',
    subtitle: 'אני מפתח אתרים ואפלקציות מקצה לקצה, או במילים אחרות full-stack developer',
    text: "בשנה האחרונה גיליתי תשוקה מטורפת לתכנות,\n" +
        " תשוקה שגורמת לי  להתעורר לפני קריאת התרנגול.\n" +
        " זה תמיד היה שם בעצם,\n מגיל קטן אהבתי לשבת שעות על המחשב.\n" +
        " תמיד אהבתי מתמטיקה ולוגיקה, והיום זה בא לידי ביטוי בכתיבת קוד.\n\n" +
        " שמח לעבוד במקצוע שיכול לעזור ולהשפיע על אנשים רבים ושם אותי בעמדה של יוצר, אמן.\n" +
        " מפתח על פי שיטת המצוינות הגורסת כי קודם כל יש להביא תוצאות ואחר כך לשפר אותם,\n זה כדי למנוע תקיעויות מיותרות," +
        " שנובעות מהרצון שהכל יהיה מושלם.\n\n נשוי לאשתי האהובה- רייצ'ל, ואב לשלושה ילדים מתוקים ותוכית.\n" +
        " חוץ מהחולשה שלי לכתיבת קוד \nאני גם מאוד אוהב היסטוריה, חינוך ובעלי חיים ובייחוד תוכים.\n" +
        "\nלאחרונה התחלתי גם לכתוב פוסטים בנושא תכנות,\n תוכלו למצוא אותם בפרופיל הפייסבוק שלי" ,
  })
}
</script>

<style scoped>
.tab{
  padding: 0 2rem 0 0;
  margin: 0;
}
.pre-formatted {
  white-space: pre-wrap; /* 👈 this is the important part */
  padding: 1rem;
}

</style>
