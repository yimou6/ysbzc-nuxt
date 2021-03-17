<template>
  <div class="container">
    <div class="archive" v-for="item of arr" :key="item.title">
      <div class="archive-title">{{ item.title }}</div>
      <div class="archive-content">
        <div class="archive-item" v-for="child of item.list" :key="child.title">
          <div>{{ child.title }}</div>
          <div>{{ child.date }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [
        {
          title: '2021/03/04',
          list: [
            { title: '让 promise 在发生异常时 中断代码执行的三种方式1', date: '2021/03/04' },
            { title: '让 promise 在发生异常时 中断代码执行的三种方式2', date: '2021/03/04' },
            { title: '让 promise 在发生异常时 中断代码执行的三种方式3', date: '2021/03/04' },
            { title: '让 promise 在发生异常时 中断代码执行的三种方式4', date: '2021/03/04' },
            { title: '让 promise 在发生异常时 中断代码执行的三种方式5', date: '2021/03/04' },
            { title: '让 promise 在发生异常时 中断代码执行的三种方式6', date: '2021/03/04' }
          ]
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.archive {
  margin: 1rem auto;
  .archive-title {
    color: #767676;
    font-size: 0.9rem;
    &::before {
      content: "#";
      color: #3d5ace;
      font-size: 1rem;
      padding-right: 0.6rem;
    }
  }
  .archive-content {
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
    flex-wrap: wrap;
    .archive-item {
      color: #505050;
      padding: 0.6rem;
      width: 30%;
      background-color: #ffffff;
      border-left: 0.1rem solid #f5f5f5;
      border-top: 0.1rem solid #f5f5f5;
      box-sizing: border-box;
      transition: all 0.3s;
      position: relative;
      div:nth-child(1) {
        font-size: 0.95rem;
        cursor: pointer;
      }
      div:nth-child(2) {
        margin-top: 1.5rem;
        font-size: 0.8rem;
        text-align: right;
      }
      &::after {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border-bottom: 0 solid #505050;
        transition: all 0.3s;
      }
      &:hover::after {
        border-bottom: 0.4rem solid #505050;
      }
    }
    @media screen and (max-width: 375px){
      .archive-item {
        width: 100%;
      }
    }
    @media screen and (min-width: 376px){
      .archive-item {
        width: 50%;
      }
    }
    @media screen and (min-width: 768px){
      .archive-item {
        width: 33%;
      }
    }
  }
}
</style>
