


<template>
  <div class="container py-5">
    <NavTabs />
    <!-- 餐廳類別標籤 RestaurantsNavPills -->
    <RestaurantsNavPills :categories="categories" />
    <div class="row">
      <!-- 餐廳卡片 RestaurantCard-->
      <RestaurantCard
        v-for="restaurant in restaurants"
        :key="restaurant.id"
        :initial-restaurant="restaurant"
      />
    </div>

    <!-- 分頁標籤 RestaurantPagination -->
    <RestaurantsPagination
      :categoryId="categoryId"
      :currentPage="currentPage"
      :totalPage="totalPage"
      :previousPage="previousPage"
      :nextPage="nextPage"
    />
  </div>
</template>

<script>
// ./src/App.vue
import NavTabs from "./../components/NavTabs";
import RestaurantCard from "./../components/RestaurantCard";
import RestaurantsNavPills from "./../components/RestaurantsNavPills";
import RestaurantsPagination from "./../components/RestaurantsPagination";

const dummyData = {
  restaurants: [
    {
      id: 1,
      name: "Barney Bins",
      tel: "004-298-3723 x3557",
      address: "362 Shanahan Square",
      opening_hours: "08:00",
      description: "Mollitia nam dolores recusandae rerum quae corpori",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=81.54199831611012",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 2,
      name: "Darrel Kris",
      tel: "1-795-583-3216 x52775",
      address: "93112 Delmer Street",
      opening_hours: "08:00",
      description: "Amet quae aut consectetur rem est recusandae.",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=51.91660239396532",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 3,
      name: "Odessa Bayer",
      tel: "1-020-083-8875",
      address: "010 MacGyver Isle",
      opening_hours: "08:00",
      description: "Consequatur dicta quia dignissimos vero expedita c",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=60.947263783379135",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 4,
      name: "Andrew West",
      tel: "620.445.0712 x682",
      address: "5477 Waters Forest",
      opening_hours: "08:00",
      description: "Non culpa enim officia. Dolore aut odio quasi cons",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=84.81282549948368",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 4,
      Category: {
        id: 4,
        name: "墨西哥料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 5,
      name: "Mrs. Kevon Bayer",
      tel: "339-777-3642 x375",
      address: "249 Cremin Islands",
      opening_hours: "08:00",
      description: "rerum",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=93.59560669582562",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 6,
      name: "Madison Cartwright",
      tel: "966-144-5642",
      address: "8756 Rau Mountains",
      opening_hours: "08:00",
      description: "Quo ipsam hic deleniti doloribus et suscipit sed e",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=64.20912451374615",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 1,
      Category: {
        id: 1,
        name: "中式料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 7,
      name: "Enola Kerluke",
      tel: "446-213-9564",
      address: "8031 Torphy Estate",
      opening_hours: "08:00",
      description: "Asperiores accusantium dolor sunt. Ipsam provident",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=39.30880734931963",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 5,
      Category: {
        id: 5,
        name: "素食料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 8,
      name: "Lucie Powlowski",
      tel: "674-483-1420 x23137",
      address: "734 Madyson Views",
      opening_hours: "08:00",
      description: "Voluptas accusantium dolorum iure et ratione volup",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=74.78485125157346",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 5,
      Category: {
        id: 5,
        name: "素食料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 9,
      name: "Jayne King",
      tel: "(729) 248-6799",
      address: "40683 Farrell Street",
      opening_hours: "08:00",
      description: "Ut quasi laudantium qui aliquam. Ducimus deserunt ",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=61.60362717948138",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 2,
      Category: {
        id: 2,
        name: "日本料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
    {
      id: 10,
      name: "Alyce Muller",
      tel: "(915) 780-7485",
      address: "466 Anabelle Canyon",
      opening_hours: "08:00",
      description: "Sit temporibus et ut. Consequuntur dolorum reprehe",
      image:
        "https://loremflickr.com/320/240/restaurant,food/?random=97.44891141281596",
      viewCounts: 0,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      CategoryId: 3,
      Category: {
        id: 3,
        name: "義大利料理",
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      isFavorited: false,
      isLiked: false,
    },
  ],
  categories: [
    {
      id: 1,
      name: "中式料理",
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
    },
    {
      id: 2,
      name: "日本料理",
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
    },
    {
      id: 3,
      name: "義大利料理",
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
    },
    {
      id: 4,
      name: "墨西哥料理",
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
    },
    {
      id: 5,
      name: "素食料理",
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
    },
    {
      id: 6,
      name: "美式料理",
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
    },
    {
      id: 7,
      name: "複合式料理",
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
    },
  ],
  categoryId: "",
  page: 1,
  totalPage: [1, 2, 3, 4, 5],
  prev: 1,
  next: 2,
};

export default {
  components: {
    NavTabs,
    RestaurantCard,
    RestaurantsNavPills,
    RestaurantsPagination,
  },
  data() {
    return {
      restaurants: [],
      categories: [],
      categoryId: -1,
      currentPage: 1,
      totalPage: [],
      previousPage: -1,
      nextPage: -1,
    };
  },
  created() {
    this.fetchRestaurants();
  },
  methods: {
    fetchRestaurants() {
      const {
        restaurants,
        categories,
        categoryId,
        page,
        totalPage,
        prev,
        next,
      } = dummyData;

      this.restaurants = restaurants;
      this.categories = categories;
      this.categoryId = categoryId;
      this.currentPage = page;
      this.totalPage = totalPage;
      this.previousPage = prev;
      this.nextPage = next;
    },
  },
};
</script>
