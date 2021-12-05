<template>
  <div class="container py-5">
    <NavTabs />
    <h1 class="mt-5">最新動態</h1>
    <hr />
    <div class="row">
      <div class="col-md-6">
        <h3>最新餐廳</h3>
        <NewestRestaurants :restaurants="restaurants" />
        <!-- 最新餐廳 NewestRestaurants -->
      </div>
      <div class="col-md-6">
        <!-- 最新評論 NewestComments-->
        <h3>最新評論</h3>
        <NewestComments :comments="comments" />
      </div>
    </div>
  </div>
</template>
<script>
// ./src/App.vue
import NavTabs from "./../components/NavTabs";
import NewestRestaurants from "./../components/NewestRestaurants";
import NewestComments from "./../components/NewestComments";

const dummyData = {
  restaurants: [
    {
      id: 1,
      name: "Barney Bins",
      tel: "004-298-3723 x3557",
      address: "362 Shanahan Square",
      opening_hours: "08:00",
      description:
        "Mollitia nam dolores recusandae rerum quae corporis ipsa ut deleniti. Aut quaerat veniam sint et consequatur voluptas omnis consequatur inventore. Eos culpa sint enim et sunt aut dolorum voluptatem. Quia assumenda cum. Aut ab similique. Vel veniam est ratione earum reprehenderit optio ut eum.",
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
    },
    {
      id: 3,
      name: "Odessa Bayer",
      tel: "1-020-083-8875",
      address: "010 MacGyver Isle",
      opening_hours: "08:00",
      description:
        "Consequatur dicta quia dignissimos vero expedita consectetur rerum ea doloribus. Ipsam fugit quos dolores aut. Laboriosam ut fuga corporis numquam veniam.",
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
    },
    {
      id: 4,
      name: "Andrew West",
      tel: "620.445.0712 x682",
      address: "5477 Waters Forest",
      opening_hours: "08:00",
      description:
        "Non culpa enim officia. Dolore aut odio quasi consequuntur et autem. Qui nam suscipit nesciunt similique. Commodi eos ea nam qui incidunt doloremque quo.",
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
    },
    {
      id: 6,
      name: "Madison Cartwright",
      tel: "966-144-5642",
      address: "8756 Rau Mountains",
      opening_hours: "08:00",
      description:
        "Quo ipsam hic deleniti doloribus et suscipit sed enim. Similique soluta voluptatem officiis officia doloremque doloremque consequatur rerum. Deleniti voluptatem incidunt ratione aperiam dolores.",
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
    },
    {
      id: 7,
      name: "Enola Kerluke",
      tel: "446-213-9564",
      address: "8031 Torphy Estate",
      opening_hours: "08:00",
      description:
        "Asperiores accusantium dolor sunt. Ipsam provident dolorum. Est eveniet beatae exercitationem quae id et ut sunt. Eos minima itaque vero quos in sed dolores illum.",
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
    },
    {
      id: 8,
      name: "Lucie Powlowski",
      tel: "674-483-1420 x23137",
      address: "734 Madyson Views",
      opening_hours: "08:00",
      description:
        "Voluptas accusantium dolorum iure et ratione voluptas eos quos similique. Sed assumenda sed illum laboriosam deleniti fuga. Consequuntur ullam vel doloribus et culpa ducimus. Tempore explicabo minus ut rerum placeat sequi. Cumque non nesciunt explicabo similique non aut.",
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
    },
    {
      id: 9,
      name: "Jayne King",
      tel: "(729) 248-6799",
      address: "40683 Farrell Street",
      opening_hours: "08:00",
      description:
        "Ut quasi laudantium qui aliquam. Ducimus deserunt eos rem tenetur non occaecati ut non voluptatem. Dolorem vitae tempora maiores. Voluptatem vel nesciunt qui exercitationem ea ipsa cupiditate ab. Qui veritatis et blanditiis aut nihil dolore possimus dolorum.",
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
    },
    {
      id: 10,
      name: "Alyce Muller",
      tel: "(915) 780-7485",
      address: "466 Anabelle Canyon",
      opening_hours: "08:00",
      description:
        "Sit temporibus et ut. Consequuntur dolorum reprehenderit temporibus. Dolores natus at qui rerum officiis delectus temporibus qui blanditiis. Necessitatibus non quos et. Eos in fugit et. Ipsam maiores ut.\n \rVeritatis vitae eum molestias. Incidunt non officiis rerum eligendi quisquam quibusdam laudantium voluptatum vero. Reiciendis dolor sed vel assumenda impedit et excepturi in. Deleniti maxime sunt nulla rerum est. Consectetur sed cum quia. Inventore adipisci ut sit repellendus delectus veritatis dignissimos rerum cupiditate.\n \rA ut minus nulla sed vitae repudiandae impedit cum cupiditate. Qui sed quo expedita sint. Optio rem culpa sunt. Dignissimos sit asperiores eligendi tempore et ipsam est rerum in. Consequuntur consequatur ut necessitatibus nihil aut autem.",
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
    },
  ],
  comments: [
    {
      id: 3,
      text: "Voluptate ducimus non.",
      UserId: 1,
      RestaurantId: 3,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$98fqfRBwUVZ3PsxsPHI2..UCK/Vvwyo/7UVVmxaeqvYZi2AUyKCZK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 3,
        name: "Odessa Bayer",
        tel: "1-020-083-8875",
        address: "010 MacGyver Isle",
        opening_hours: "08:00",
        description:
          "Consequatur dicta quia dignissimos vero expedita consectetur rerum ea doloribus. Ipsam fugit quos dolores aut. Laboriosam ut fuga corporis numquam veniam.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=60.947263783379135",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 1,
      },
    },
    {
      id: 24,
      text: "Qui voluptas vel rerum eius voluptas accusamus ea.",
      UserId: 1,
      RestaurantId: 24,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$98fqfRBwUVZ3PsxsPHI2..UCK/Vvwyo/7UVVmxaeqvYZi2AUyKCZK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 24,
        name: "Gideon Corkery",
        tel: "(743) 623-3189 x3010",
        address: "609 Wolff Port",
        opening_hours: "08:00",
        description:
          "Itaque quaerat ducimus totam et deleniti quasi eos omnis. Sint id placeat voluptatem explicabo eum autem qui non. Quod vel omnis illo culpa.\n \rFugit vitae et nostrum quia. Veritatis et qui perferendis temporibus. Libero natus ratione est tempore cupiditate inventore. Repudiandae dolorum reprehenderit possimus beatae quo nam ut voluptates molestiae. Dicta provident nemo minima aut. Consequatur non omnis ut non quo optio.\n \rExpedita qui voluptas aspernatur qui dolor vel facilis voluptatem omnis. Porro facilis reiciendis quibusdam possimus. Consequuntur perspiciatis quam possimus veritatis fugit at reiciendis quia qui.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=83.3150644102578",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 3,
      },
    },
    {
      id: 40,
      text: "Tempore ratione natus sunt laudantium suscipit doloremque atque accusamus.",
      UserId: 1,
      RestaurantId: 40,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$98fqfRBwUVZ3PsxsPHI2..UCK/Vvwyo/7UVVmxaeqvYZi2AUyKCZK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 40,
        name: "Miss Leo Kirlin",
        tel: "343-956-9979 x584",
        address: "305 Evangeline Squares",
        opening_hours: "08:00",
        description:
          "Qui qui et fugit aut ut dignissimos officiis veritatis. Nihil sint velit voluptates itaque alias ut inventore aperiam voluptatem. Culpa eligendi deserunt inventore delectus quisquam qui voluptate dolorum. Eaque sint veritatis accusamus eius eum sit ducimus quisquam.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=97.07295215817133",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 4,
      },
    },
    {
      id: 65,
      text: "Qui quaerat quaerat commodi voluptatem tenetur velit.",
      UserId: 1,
      RestaurantId: 15,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$98fqfRBwUVZ3PsxsPHI2..UCK/Vvwyo/7UVVmxaeqvYZi2AUyKCZK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 15,
        name: "Valentine Upton",
        tel: "932-781-9776",
        address: "72602 Caesar Dam",
        opening_hours: "08:00",
        description: "animi in sequi",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=12.377855632016788",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 5,
      },
    },
    {
      id: 109,
      text: "Quo ratione velit aut.",
      UserId: 1,
      RestaurantId: 9,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$98fqfRBwUVZ3PsxsPHI2..UCK/Vvwyo/7UVVmxaeqvYZi2AUyKCZK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 9,
        name: "Jayne King",
        tel: "(729) 248-6799",
        address: "40683 Farrell Street",
        opening_hours: "08:00",
        description:
          "Ut quasi laudantium qui aliquam. Ducimus deserunt eos rem tenetur non occaecati ut non voluptatem. Dolorem vitae tempora maiores. Voluptatem vel nesciunt qui exercitationem ea ipsa cupiditate ab. Qui veritatis et blanditiis aut nihil dolore possimus dolorum.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=61.60362717948138",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 2,
      },
    },
    {
      id: 127,
      text: "Laudantium voluptatum est.",
      UserId: 1,
      RestaurantId: 27,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$98fqfRBwUVZ3PsxsPHI2..UCK/Vvwyo/7UVVmxaeqvYZi2AUyKCZK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 27,
        name: "Dexter Harber",
        tel: "1-517-330-2681 x890",
        address: "38792 Barton Circles",
        opening_hours: "08:00",
        description:
          "Illum aut autem quam placeat molestias.\nEt sit ut ratione et.\nIste fuga ut reiciendis.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=92.0830795729816",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 2,
      },
    },
    {
      id: 144,
      text: "Architecto labore eligendi officia occaecati ut architecto architecto ut.",
      UserId: 1,
      RestaurantId: 44,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 1,
        name: "root",
        email: "root@example.com",
        password:
          "$2a$10$98fqfRBwUVZ3PsxsPHI2..UCK/Vvwyo/7UVVmxaeqvYZi2AUyKCZK",
        isAdmin: true,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 44,
        name: "Mr. Jerad Cartwright",
        tel: "154.663.0609 x077",
        address: "441 Bianka Route",
        opening_hours: "08:00",
        description:
          "Harum omnis error. Temporibus qui dignissimos iste ipsam expedita magnam fugit nam. Quas molestias et autem eos ut porro qui modi. Voluptatibus consequatur exercitationem corporis vel. Magnam reiciendis sit quos exercitationem sapiente amet omnis iusto excepturi.\n \rOptio dicta explicabo ea dolorum nihil. Est explicabo possimus accusamus commodi. Voluptatem enim non quos maxime eveniet quibusdam sed doloribus voluptates.\n \rAliquid nemo sint nisi aut atque. Qui voluptate molestiae praesentium et ducimus accusantium voluptatem magni. Adipisci consequatur expedita.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=0.41995192558272887",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 1,
      },
    },
    {
      id: 23,
      text: "Ad quis dolores.",
      UserId: 2,
      RestaurantId: 23,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 2,
        name: "user1",
        email: "user1@example.com",
        password:
          "$2a$10$xh31GsF.AWwhLdJOpEHS7uAf6RRoNM5NXvbUyofzG1fD3kO7sYjUW",
        isAdmin: false,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 23,
        name: "Devonte Heidenreich",
        tel: "069-216-3960 x8117",
        address: "006 Kelley Camp",
        opening_hours: "08:00",
        description:
          "Debitis nesciunt est qui et quia aperiam voluptas. Placeat at magni animi sint eveniet. Minima qui hic sed consequatur voluptas voluptatum ad facere. Voluptate accusamus necessitatibus autem ipsa neque eaque autem nostrum. Voluptatum vero consequatur cum tempore consequatur illo. Voluptate iure corrupti quibusdam at dolorem eos.\n \rSunt ut assumenda sit. Provident et vel laborum et maxime nulla quia rem tempora. Est aut maiores tempora libero qui enim.\n \rLaudantium fugit quam quis. Quis asperiores vel perspiciatis aut autem aperiam asperiores in. Impedit et consectetur fugit reiciendis. Nesciunt sint distinctio officiis minus quae vitae provident animi omnis. Quia voluptas incidunt delectus et quibusdam consequatur sequi non. Commodi cupiditate voluptas harum quis.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=1.4180399146648481",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 5,
      },
    },
    {
      id: 42,
      text: "Eum soluta ducimus id.",
      UserId: 2,
      RestaurantId: 42,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 2,
        name: "user1",
        email: "user1@example.com",
        password:
          "$2a$10$xh31GsF.AWwhLdJOpEHS7uAf6RRoNM5NXvbUyofzG1fD3kO7sYjUW",
        isAdmin: false,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 42,
        name: "Carlotta Huels",
        tel: "108.009.8605",
        address: "00118 Major Via",
        opening_hours: "08:00",
        description: "aliquid dicta earum",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=74.64870687055658",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 4,
      },
    },
    {
      id: 71,
      text: "Cumque provident fugit.",
      UserId: 2,
      RestaurantId: 21,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      User: {
        id: 2,
        name: "user1",
        email: "user1@example.com",
        password:
          "$2a$10$xh31GsF.AWwhLdJOpEHS7uAf6RRoNM5NXvbUyofzG1fD3kO7sYjUW",
        isAdmin: false,
        image: null,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
      },
      Restaurant: {
        id: 21,
        name: "Elza Kilback",
        tel: "(810) 645-7939 x8340",
        address: "86786 Kathleen Drive",
        opening_hours: "08:00",
        description:
          "Voluptatem optio tenetur aut et aperiam officiis eum voluptatum.\nIn quod fugit mollitia blanditiis sit.\nAd temporibus sint ut aspernatur.\nDolorum et at.",
        image:
          "https://loremflickr.com/320/240/restaurant,food/?random=39.7177880457044",
        viewCounts: 0,
        createdAt: "2021-11-12T14:39:42.000Z",
        updatedAt: "2021-11-12T14:39:42.000Z",
        CategoryId: 4,
      },
    },
  ],
};

export default {
  components: {
    NavTabs,
    NewestRestaurants,
    NewestComments,
  },
  data() {
    return {
      restaurants: [],
      comments: [],
    };
  },
  created() {
    this.fetchFeeds();
  },
  methods: {
    fetchFeeds() {
      this.restaurants = dummyData.restaurants;
      this.comments = dummyData.comments.filter(
        (comment) => comment.Restaurant && comment.text
      );
    },
  },
};
</script>