<!-- 内容列表 -->
<template>
  <div class="timeline-entry-list">
    <div class="entry-list-container">
      <header class="list-header" style="display: ">
        <nav class="list-nav">
          <ul class="nav-list left">
            <li class="nav-item active">
              <a href="/">推荐</a>
            </li>
            <li class="nav-item"><a href="/?sort=newest">最新</a></li>
            <li class="nav-item">
              <a href="/?sort=three_days_hottest">热榜</a>
            </li>
          </ul>
        </nav>
        <div class="drop-down-area"></div>
      </header>
      <div class="entry-list-wrap">
        <div class="entry-list list">
          <li class="item" v-for="(p, index) in ress" :key="p.id">
            <div v-for="(p1, index1) in p.data" :key="p1.id">
              <div
                class="advertisement"
                enable-dislike-button="true"
                v-show="flag[index][index1]"
              >
                <div class="meta-container">
                  <div class="user-message">
                    <a href="" target="_blank" class="userbox">
                      <div class="popover-box user-popover">
                        {{ p1.item_info.author_name }}
                      </div>
                    </a>
                  </div>
                  <div class="dividing"></div>
                  <div class="date">1天前</div>
                </div>
                <div class="tag">广告</div>
                <div class="main">
                  <div class="info-box">
                    <a href="" target="_blank" class="title">
                      {{ p1.item_info.title }}
                    </a>
                    <a href="" target="_blank" class="description">
                      {{ p1.item_info.brief }}
                    </a>
                  </div>
                  <img
                    v-bind:src="p1.item_info.picture"
                    alt=""
                    class="lazy thumb"
                  />
                </div>
              </div>

              <div
                class="entry"
                enable-dislike-button="true"
                v-show="!flag[index][index1]"
                v-if="p1.item_info.author_user_info"
              >
                <div class="meta-container">
                  <a href="" target="_blank" class="user-message">
                    <div class="popover-box user-popover">
                      {{ p1.item_info.author_user_info.user_name }}
                    </div>
                  </a>
                  <div class="dividing"></div>
                  <div class="date">2天前</div>
                  <div class="tag_list"></div>
                </div>
                <!-- <div class="tag">广告</div> -->
                <div
                  class="content-wrapper"
                  style="border-bottom: 1px solid rgba(228, 230, 235, 0.5)"
                >
                  <div class="content-main">
                    <div class="title-row">
                      <a href="" target="_blank" class="title">
                        <!-- {{ p.item_info.author_user_info.author_name }} -->
                        {{ p1.item_info.article_info.title }}
                      </a>
                    </div>
                    <div class="abstract">
                      <a href="" target="_blank" class="description">
                        {{ p1.item_info.article_info.brief_content }}
                      </a>
                    </div>
                    <ul class="action-list jh-ti,eline-action-area">
                      <li class="item view">
                        <i></i>
                        <span>{{ p1.item_info.article_info.view_count }}</span>
                      </li>
                      <li class="item like">
                        <i></i>
                        <span>{{ p1.item_info.article_info.digg_count }}</span>
                      </li>
                      <li class="item comment">
                        <i></i>
                        <span>{{
                          p1.item_info.article_info.comment_count
                        }}</span>
                      </li>
                    </ul>
                  </div>
                  <img
                    v-if="p1.item_info.article_info.cover_image"
                    v-bind:src="p1.item_info.article_info.cover_image"
                    alt=""
                    class="lazy thumb"
                  />
                </div>
              </div>
            </div>
          </li>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      res: [],
      ress: [],
      flag: [],
    };
  },
  methods: {
    chooseType() {
      // let ress = this.res;
      var _this = this;
      let nress = this.ress;
      console.log(this.ress.length);
      for (let i = 0; i < nress.length; i++) {
        // console.log(nress[i].data.length);
        this.flag.push([]);

        for (let t = 0; t < nress[i].data.length; t++) {
          // console.log(1);
          // console.log(nress[i].data[t].item_type);
          if (nress[i].data[t].item_type == 14) {
            _this.flag[i].push(true);
          } else {
            _this.flag[i].push(false);
          }
          // console.log(ress[t].item_type);
        }
      }
      console.log(this.flag);
    },
    getData() {
      {
        axios.get("./static/data.json").then((res) => {
          //用axios的方法引入地址
          // obj=JSON.parse(jsonstr1);
          this.res = res.data[0].data;
          this.ress = res.data;
          console.log(this.res);
          console.log(this.ress);
          this.chooseType();
          //赋值
          // console.log(res.data[0].data[0].item_info.user_id);
          // console.log(res.data);
        });
      }
    },
  },
  created() {
    this.getData();
    // console.log(this.res);
    // this.chooseType();
  },
  mounted() {
    // console.log(this.res.data[0]);
    // this.getData();
    // this.chooseType();
  },
};
</script>

<style>
.action-list > .item.comment i {
  background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAABYlAAAWJQFJUiTwAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAKRSURBVHgB7VZNbtpQEJ55BlR15RvUOUHTG5ATJD1BQ9NU6gq8JKiKoyrJ0u2qUmkFOUGaE5TegJwg7gnqLRh7MvMwwiDbYHCUDZ9kHph5M9+bN38AO+zwzEAoiEv3xz4v/KAFiK/0S6J/qPCBoui+Y38cFlC3HgHH7Zk1FTXZUIt/mivEPVY6GFFw4difPNiWwNW3X+dLhj1iA3JqProXq7EQ8TVoz4A1147OWfPkAjYhcO1+twirt7FSEexPiG4+26cDyMEXt1s3AI7Z+LsZ4TEFB1newBzjf2B6Gi8kaqwyvEpHFgmVtjmxcTgm401R44I2G0M2KjpEV5W9KbG0koC+8znrt47d8GFDCAk+gJCQwNyvwqS1LLNwBbHbHuQ7G99bJ4rXgY4LRPGqz4T2koda8EAERl2zIrory7hArlBnDmdSDSbHyf8WrwDVNHKV0YOyQdGNXhAPMwlgnHKjaHQPJUNBOEjamL9fhI7SMt0/Q3uu08wjoJGWLk+FZQKefLyEwIKSETcxwTCbANFfWQLAIygZCFifrjkEQq73WgixCaUziHWi+p1JIC65Hj/mpdt1oCQkq2u7+f4uk4BAGo8minguFQy2hFRXvlonqTuXgK5aRLqHc/m8vXK7LdgCE6hYskolTGtqqWnYsU+dmITJrnCvv/7sOXKSDVCBiScrJgeVBHInIokDuYqEsB5KQqgMl7uk1A4DwrpCkFLLExL0x1HAWfXCr2H4X2TOWh+wEAGB7pBQcRITzgwymvmxEilcVtp+cX1cfs20Drv2VKyDSVUPI4Ij3lRPEfFJclzXEvIQlXhioZ4QYaNjn/Q3IrAMiQmDA0wB+QGEflr/ENK6xXOXFS8QRQdFx/YdnhyP1D0hcwr1KvEAAAAASUVORK5CYII=);
}
.action-list > .item.like i {
  background-image: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAACXBIWXMAABYlAAAWJQFJUiTwAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAJ9SURBVHgB7VZNbtNQEP7GP7AkN8DcoJyA5gRNTwCR2kqsUm9YEKEaoZRl0hUSBLWcAHOCpjdIT1AfIewgTjzM+AccxwHXLRYS/STnvbyxZ743b34e8L+DcEMMhu+fERk7DLTAuAwRjjz3eVD1+xsROD75eARmr7AczDlsVyVhoCbeDt85mXHmqLtkbst0Ko9jk31aVU9tAgvYW7FxYNJ3D85eufuTOZtKYiZu3X4z/LBdRU9tAia4E0+YL7I1z+3OmPEpkWOrip7aBED0RAcb7K8KeBb/alD+LQIa+TI48kxfuAfTVSlVMlybgAafpN1RYgujopwIOzpGEhuogGuloTc8bd2j5TmS8/VfHu7t5uUaeCaRygORPaqi00JFJAVn2UuNa667xXfEeJZ+rePR+Kool7gIQg67+RpBJTvo5QMoZHPXxFLW8Tld2lhoUqMOfg/JlKjdT2Pnpwf0bDlx3worG1EnPlENF0m5OayO5+7NyjRLHXgMfCsNQhumrBviRfRAhnqyu0KAYXmpcX/BfKKekL+dvBIheOUddkuNK7QO6A43ycXDvolYr5OtGTnlD3VU41rVZLdfccvIipMYDdYINAHZZJyicgR+4wQ0hbVH6Px7RBeNE9BM0lGbVxorTRNImhcxf8mvNxcDafOywBM0TUCqqEa/I09QbF6NECDQdjKuN6hGCJSlX2MENqXfGgFKS6hlmA9wi7hvLJ/qWEy/DL96AfMlEXWkU/mD0XiCkjud7kRk56iOltwRYz3ShM7KXlhpx4PheBR3qxzS6zbSi0YtyOZe9919D38ioNC2vIDl6NyQC2bWtzWVomvf93gWwg7KXH+HfwY/AGsn+Lf3Dim6AAAAAElFTkSuQmCC);
}
.action-list,
.action-list > .item {
  display: flex;
  align-items: center;
}
.action-list > .item {
  position: relative;
  margin-right: 20px;
  font-size: 13px;
  line-height: 20px;
  color: #4e5969;
  flex-shrink: 0;
}
i + span {
  margin-left: 0.6rem;
}
.action-list > .item span {
  margin-left: 4px;
}
i {
  font-style: italic;
}
.action-list > .item i {
  display: block;
  width: 16px;
  height: 16px;
  background-size: 100%;
}
.action-list > .item.view i {
  background-image: url(https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/view.1eda8fa.png);
}
.thumb {
  flex: 0 0 auto;
  width: 120px;
  height: 80px;
  margin-left: 24px;
  background-color: #fff;
  border-radius: 2px;
}
.abstract a {
  color: #86909c;
  font-size: 13px;
  line-height: 22px;
  display: -webkit-box;
  overflow: hidden;
  text-overflow: ellipsis;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 1;
}
.abstract {
  margin-bottom: 10px;
}
.title {
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  color: #1d2129;
  width: 100%;
  display: -webkit-box;
  overflow: hidden;
  text-overflow: ellipsis;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 1;
}
.title-row {
  display: flex;
  margin-bottom: 8px;
}
.content-wrapper {
  display: flex;
  padding-bottom: 12px;
  border-bottom: 1px solid #e5e6eb;
  margin-top: 10px;
  width: 100%;
}
.content-wrapper .content-main {
  flex: 1 1 auto;
}
.meta-container .user-message:hover {
  color: #1d7dfa;
}
.advertisement .meta-container .user-message .userbox:hover {
  color: #1d7dfa;
}
.thumb {
  flex: 0 0 auto;
  width: 120px;
  height: 80px;
  margin-left: 24px;
  background-color: #fff;
  border-radius: 2px;
}
.thumb {
  flex: 0 0 auto;
  width: 120px;
  height: 80px;
  margin-left: 24px;
  border-radius: 2px;
}
.lazy {
  position: relative;
  -o-object-fit: cover;
  object-fit: cover;
}
img {
  border-style: none;
}
.meta-container .user-message {
  display: flex;
  align-items: center;
  margin-right: 8px;
  max-width: 162px;
  font-size: 13px;
  line-height: 22px;
  color: #4e5969;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  word-break: break-all;
}

.entry .main .info-box .description {
  font-weight: 400;
  font-size: 13px;
  line-height: 22px;
  color: #86909c;
  display: -webkit-box;
  overflow: hidden;
  text-overflow: ellipsis;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
}
.entry .main .info-box .title {
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  color: #1d2129;
  margin-bottom: 8px;
  /* 当父元素设置了这个属性之后，子元素变成内联元素(子元素的子元素不会受影响，感觉和flex十分类似)，高度默认占满父元素，当所有子元素的宽度超过父元素的宽度的时候，他不会自动换行，会继续占领那一行，父元素的宽度不会改变 */
  display: -webkit-box;
  overflow: hidden;
  /* 默认值:clip;
  适用于:所有元素
  clip:当前对象内文本溢出时不显示省略标记(...),而是将溢出部分裁剪。
  ellipsis:当对象内文本一处时显示省略标记(...)。 */
  text-overflow: ellipsis;
  /* 从上到下垂直排列子元素（设置伸缩盒子的子元素排列方式） */
  -webkit-box-orient: vertical;
  /* 这个属性不是css的规范属性，需要组合上面两个属性，表示显示的行数,实现标题只实现一行。 */
  -webkit-line-clamp: 1;
}
.entry .main .info-box .title:visited {
  /* color: #86909c; */
}
.entry .main .info-box {
  flex-grow: 1;
}
.entry .main {
  margin-top: 6px;
  padding-bottom: 12px;
  display: flex;
  border-bottom: 1px solid #e5e6eb;
}
.entry .tag {
  position: absolute;
  top: 12px;
  right: 20px;
  border: 1px solid #c9cdd4;
  box-sizing: border-box;
  border-radius: 2px;
  line-height: 18px;
  width: 42px;
  text-align: center;
  color: #c9cdd4;
  font-size: 13px;
}
.entry .meta-container .dividing {
  width: 1px;
  height: 14px;
  background: #e5e6eb;
  margin: 0 8px;
}
.entry .meta-container .date {
  line-height: 22px;
  font-size: 13px;
  color: #86909c;
}
.entry {
  position: relative;
  cursor: pointer;
  padding: 12px 20px 0;
}
.entry .meta-container,
.entry .meta-container .user-message {
  display: flex;
  align-items: center;
}
.entry .meta-container .user-message .userbox {
  max-width: 162px;
  font-size: 13px;
  line-height: 22px;
  color: #4e5969;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  word-break: break-all;
}
.entry {
  cursor: pointer;
  position: relative;
  background: #fff;
  padding: 12px 20px 0;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.advertisement .main .info-box .description {
  font-weight: 400;
  font-size: 13px;
  line-height: 22px;
  color: #86909c;
  display: -webkit-box;
  overflow: hidden;
  text-overflow: ellipsis;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
}
.advertisement .main .info-box .title {
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  color: #1d2129;
  margin-bottom: 8px;
  /* 当父元素设置了这个属性之后，子元素变成内联元素(子元素的子元素不会受影响，感觉和flex十分类似)，高度默认占满父元素，当所有子元素的宽度超过父元素的宽度的时候，他不会自动换行，会继续占领那一行，父元素的宽度不会改变 */
  display: -webkit-box;
  overflow: hidden;
  /* 默认值:clip;
  适用于:所有元素
  clip:当前对象内文本溢出时不显示省略标记(...),而是将溢出部分裁剪。
  ellipsis:当对象内文本一处时显示省略标记(...)。 */
  text-overflow: ellipsis;
  /* 从上到下垂直排列子元素（设置伸缩盒子的子元素排列方式） */
  -webkit-box-orient: vertical;
  /* 这个属性不是css的规范属性，需要组合上面两个属性，表示显示的行数,实现标题只实现一行。 */
  -webkit-line-clamp: 1;
}
.advertisement .main .info-box .title:visited {
  color: #86909c;
}
.advertisement .main .info-box {
  flex-grow: 1;
}
.advertisement .main {
  margin-top: 6px;
  padding-bottom: 12px;
  display: flex;
  border-bottom: 1px solid #e5e6eb;
}
.advertisement .tag {
  position: absolute;
  top: 12px;
  right: 20px;
  border: 1px solid #c9cdd4;
  box-sizing: border-box;
  border-radius: 2px;
  line-height: 18px;
  width: 42px;
  text-align: center;
  color: #c9cdd4;
  font-size: 13px;
}
.advertisement .meta-container .dividing {
  width: 1px;
  height: 14px;
  background: #e5e6eb;
  margin: 0 8px;
}
.advertisement .meta-container .date {
  line-height: 22px;
  font-size: 13px;
  color: #86909c;
}
.advertisement {
  position: relative;
  cursor: pointer;
  padding: 12px 20px 0;
}
.advertisement .meta-container,
.advertisement .meta-container .user-message {
  display: flex;
  align-items: center;
}
.advertisement .meta-container .user-message .userbox {
  max-width: 162px;
  font-size: 13px;
  line-height: 22px;
  color: #4e5969;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  word-break: break-all;
}
.popover-box {
  display: inline;
}
.item {
  transition: all 0.3s ease-in;
}
.entry-list {
  width: 100%;
  background-color: #fff;
  position: relative;
}
.timeline-entry-list {
  /* margin-right: 21.667rem; */
  border-radius: 2px;
  width: 700px;
}
.entry-list-container {
  background-color: #fff;
}
.list-header {
  padding: 1.3rem 1rem;
  border-bottom: 1px solid hsla(0, 0%, 59.2%, 0.1);
}
.list-nav {
  justify-content: flex-start !important;
}
.list-header .nav-list {
  align-items: center;
  line-height: 1;
}
.list-header .list-nav,
.list-header .nav-list {
  display: flex;
  justify-content: space-between;
}
ul {
  padding: 0;
  margin: 0;
}
ul {
  display: block;
  list-style-type: disc;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
  /* padding-inline-start: 40px; */
}
.list-nav .nav-list.left .nav-item {
  font-size: 1.17rem;
}
.list-header .nav-list .nav-item.active a,
.list-header .nav-list .nav-item a:hover {
  color: #007fff;
}
a {
  text-decoration: none;
  cursor: pointer;
  color: #909090;
}
li {
  list-style: none;
  display: list-item;
  text-align: -webkit-match-parent;
}
.list-header .nav-list {
  align-items: center;
  line-height: 1;
}
a,
button,
input {
  margin: initial;
  margin-right: 5px;
}
.nav-item {
  position: relative;
  cursor: pointer;
}
.nav-item > a:before {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
nav {
  display: block;
}
body,
html {
  -webkit-font-smoothing: unset !important;
  font-family: -apple-system, system-ui, Segoe UI, Roboto, Ubuntu, Cantarell,
    Noto Sans, sans-serif, BlinkMacSystemFont, "Helvetica Neue", "PingFang SC",
    "Hiragino Sans GB", "Microsoft YaHei", Arial !important;
}
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  font-size: 12px;
  line-height: normal;
}
.list-header .left .nav-item {
  padding: 0 1.2rem;
  font-size: 1.16rem;
  border-right: 1px solid hsla(0, 0%, 59.2%, 0.2);
}
html {
  font-size: 12px;
  word-break: break-word;
  text-rendering: optimizeLegibility;
  color: #333;
  background-color: #f4f5f5;
}
</style>