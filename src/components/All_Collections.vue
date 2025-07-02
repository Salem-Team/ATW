<template>
  <div class="Collections">
    <div class="container">
      <div class="main_title">Collections</div>
      <div v-if="isLoading" class="loading">
        <font-awesome-icon :icon="['fas', 'spinner']" spin />
        <span>Loading data...</span>
      </div>

      <div class="error" v-if="error">
        <font-awesome-icon :icon="['fas', 'circle-exclamation']" />
        <div>
          {{ error }}
        </div>
      </div>
      <div class="cards_container" v-if="!error">
        <font-awesome-icon
          class="right"
          :icon="['fas', 'angle-right']"
          @click="scrollRight"
        />
        <font-awesome-icon
          class="left"
          :icon="['fas', 'angle-left']"
          @click="scrollLeft"
        />
        <div class="cards" ref="scrollContainer">
          <div
            class="card"
            :class="Collection.id"
            v-for="Collection in Collections"
            :key="Collection"
          >
            <img :src="getImage(Collection.id)" alt="" />

            <div class="caption">
              <div class="title">{{ Collection.title }}</div>
              <div>{{ Collection.description }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      error: "",
      Collections: [],
      isLoading: true,
    };
  },
  created() {
    this.GetData();
  },
  methods: {
    async GetData() {
      this.isLoading = true;
      try {
        const token = localStorage.getItem("token");
        if (!token) {
          this.error = "User is not authenticated.";
          return;
        }
        const res = await fetch(
          "http://atwltd-001-site1.qtempurl.com/api/tasks",
          {
            methods: "GET",
            headers: {
              Authorization: `Bearer ${token}`,
              "Content-Type": "application/json",
            },
          }
        );
        const data = await res.json();
        if (res.ok && data.status === 200) {
          console.log("data", data);
          this.Collections = data.data;
        }
      } catch (err) {
        this.error = "An error occurred while fetching collections.";
        console.error(err);
      } finally {
        this.isLoading = false;
      }
    },

    getImage(id) {
      try {
        return require(`../assets/Collections/${id}.jpg`);
      } catch (e1) {
        try {
          return require(`../assets/Collections/${id}.png`);
        } catch (e2) {
          console.log(e2);
        }
      }
    },

    scrollLeft() {
      this.$refs.scrollContainer.scrollLeft -= 300;
    },

    scrollRight() {
      this.$refs.scrollContainer.scrollLeft += 300;
    },
  },
};
</script>

<style scoped lang="scss">
.Collections {
  padding: 30px 30px 60px;
  background: black;
  .main_title {
    font-size: 30px;
    font-weight: bold;
    color: #fff;
    margin: 0 0 30px 0;
  }

  .cards_container {
    display: flex;
    align-items: center;
    gap: 20px;
    position: relative;

    svg {
      position: absolute;
      border: 2px solid var(--main-color);
      width: 30px;
      height: 30px;
      padding: 10px;
      border-radius: 50%;
      color: #fff;
      cursor: pointer;
      transition: 0.3s;
      background: var(--main-color);
      z-index: 2;
      &:hover {
        filter: saturate(1.5);
      }
      &.right {
        right: -25px;
      }
      &.left {
        left: -25px;
      }
    }
    .cards {
      display: flex;
      overflow-x: hidden;
      scroll-behavior: smooth;
      align-items: center;
      gap: 20px;
      position: relative;
      width: 100%;
    }
    .card {
      position: relative;
      border: 1px solid var(--main-color);
      border-radius: 10px;
      overflow: hidden;
      min-width: 24%;

      flex: 1;
      width: 250px;
      height: 300px;
      .title {
        font-weight: bold;
      }
      img {
        border-radius: 10px;
        object-fit: cover;
        width: 100%;
        height: 100%;
      }
      .caption {
        position: absolute;
        bottom: 0px;
        background: #0000008f;
        color: #fff;
        text-align: center;
        padding: 5px;
        width: 100%;
        height: 60px;
        overflow: hidden;
      }
    }
  }
}
.error {
  color: red;
  text-align: center;
  font-size: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}
.loading {
  color: var(--main-color);
  text-align: center;
  font-size: 20px;
  margin: 30px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;

  svg {
    font-size: 24px;
  }
}

@media (max-width: 720px) {
  svg {
    display: none;
  }
  .cards {
    flex-direction: column;
    .card {
      width: 100% !important;
    }
  }
}
</style>
