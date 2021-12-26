<template>
  <div class="container py-5">
    <NavTabs />
    <h1 class="mt-5">美食達人</h1>
    <hr />
    <div class="row text-center">
      <div
        class="col-3"
        v-for="user in users"
        :key="user.id"
        :initial-user="user"
      >
        <a href="#">
          <img :src="user.image" width="140px" height="140px" />
        </a>
        <h2>{{ user.name }}</h2>
        <span class="badge badge-secondary"
          >追蹤人數：{{ user.FollowerCount }}</span
        >
        <p class="mt-3">
          <button
            type="button"
            class="btn btn-danger"
            @click.stop.prevent="deleteFollow(user)"
            v-if="user.isFollowed"
          >
            取消追蹤
          </button>
          <button
            type="button"
            class="btn btn-primary"
            @click.stop.prevent="addFollow(user)"
            v-else
          >
            追蹤
          </button>
        </p>
      </div>
    </div>
  </div>
</template>
<script>
// ./src/App.vue
import NavTabs from "./../components/NavTabs";

const dummyUser = {
  users: [
    {
      id: 1,
      name: "root",
      email: "root@example.com",
      password: "$2a$10$98fqfRBwUVZ3PsxsPHI2..UCK/Vvwyo/7UVVmxaeqvYZi2AUyKCZK",
      isAdmin: true,
      image: null,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
    {
      id: 2,
      name: "user1",
      email: "user1@example.com",
      password: "$2a$10$xh31GsF.AWwhLdJOpEHS7uAf6RRoNM5NXvbUyofzG1fD3kO7sYjUW",
      isAdmin: false,
      image: null,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
    {
      id: 3,
      name: "user2",
      email: "user2@example.com",
      password: "$2a$10$zy9VyEzZmyFR4c1k422Uf.mwlrTQiH6Hx94anuJKPpa419Tgu4FdC",
      isAdmin: false,
      image: null,
      createdAt: "2021-11-12T14:39:42.000Z",
      updatedAt: "2021-11-12T14:39:42.000Z",
      Followers: [],
      FollowerCount: 0,
      isFollowed: false,
    },
  ],
};

export default {
  components: {
    NavTabs,
  },
  data() {
    return {
      users: [],
      // user: this.initialUser,
      // key: this.key,
    };
  },
  created() {
    this.fetchUsers();
  },
  methods: {
    fetchUsers() {
      const { users } = dummyUser;
      this.users = users;
    },
    // deleteFollow(targetUser) {
    //   this.currentUser = this.users[targetUser.id - 1];
    //   console.log(this.currentUser);
    //   this.currentUser.isFollowed = false;
    // },
    deleteFollow(targetUser) {
      this.users = this.users.map((user) => {
        //user 指的是 this.users 中的一筆資料
        return {
          ...user,
          //user 指的是 this.users 中的一筆資料
          isFollowed: targetUser.id === user.id ? false : user.isFollowed,
          //如果targetUser. id 等於 user.id 表示是這次要異動的該筆資料，如果是則將 isFollowed 改為 false, 不是則維持原本的值。
        };
      });
    },
    addFollow(targetUser) {
      this.users = this.users.map((user) => {
        return {
          ...user,
          isFollowed: targetUser.id === user.id ? true : user.isFollowed,
        };
      });
    },
    // addFollow(targetUser) {
    //   this.currentUser = this.users[targetUser.id - 1];
    //   console.log(this.currentUser);
    //   this.currentUser.isFollowed = true;
    // },
  },
};
</script>