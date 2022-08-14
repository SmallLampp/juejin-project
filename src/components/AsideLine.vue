

<!-- 侧边栏 -->
<template>
  <div class="main-container" style="">
    <aside class="index-aside aside" ref="init">
      <div class="signin-tip signin">
        <div class="first-line">
          <div class="icon-text">
            <img src="" alt="" />
            <span class="title wenhou">下午好!</span>
          </div>
          <button class="btn signin-btn" @click="gotoNewview()">
            <span class="btn-next">去签到</span>
          </button>
        </div>
        <div class="second-line">点亮你在社区的每一天</div>
      </div>

      <div class="sidebar-block yidong-block" ref="T">
        <div class="sidebar-block banner-block Gg1">
          <div class="banner" @mouseover="showGg1()" @mouseout="disshowGg1()">
            <a
              href="https://juejin.cn/post/7123120819437322247?utm_source=web&utm_medium=banner&utm_campaign=gengwen202208"
            >
              <img
                src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0b6a58397c77485495a051142f1d863d~tplv-k3u1fbpfcp-no-mark:480:400:0:0.awebp?"
                alt=""
                class="banner-image"
              />
            </a>
            <div class="ctrl-box">
              <i
                class="el-icon-close close-btn"
                v-show="flagGg1"
                @click="closeGg1()"
              ></i>
            </div>
          </div>
        </div>
        <div class="sidebar-block banner-block Gg2">
          <div
            class="banner banner"
            @mouseover="showGg2()"
            @mouseout="disshowGg2()"
          >
            <a
              href="https://juejin.cn/book/7117582869358182403?utm_source=web_banner&utm_medium=banner&utm_campaign=Book_zjk_0803"
            >
              <img
                src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a88a1ea956734105a5b002dfb48840cb~tplv-k3u1fbpfcp-no-mark:480:400:0:0.awebp?"
                alt=""
                class="banner-image"
              />
            </a>
            <div class="ctrl-box">
              <i
                class="el-icon-close close-btn"
                v-show="flagGg2"
                @click="closeGg2()"
              ></i>
            </div>
          </div>
        </div>

        <div
          class="sidebar-block app-download-sidebar-block sidebar-block shadow"
        >
          <div class="block-body">
            <a href="https://juejin.cn/app" class target="_blank">
              <div class="app-link">
                <img
                  src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/home.59780ae.png"
                  alt=""
                  class="qr-img"
                />
                <div class="content-box">
                  <div class="headline">下载稀土掘金APP</div>
                  <div class="desc">一个帮助开发者成长的社区</div>
                </div>
              </div>
            </a>
          </div>
        </div>
      </div>
      <!-- <div class="sidebar-block sticky-block">
        <div class="sidebar-block banner-block Gg1">
          <div
            class="banner sticky-banner"
            @mouseover="showGg1()"
            @mouseout="disshowGg1()"
          >
            <a
              href="https://juejin.cn/post/7123120819437322247?utm_source=web&utm_medium=banner&utm_campaign=gengwen202208"
            >
              <img
                src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0b6a58397c77485495a051142f1d863d~tplv-k3u1fbpfcp-no-mark:480:400:0:0.awebp?"
                alt=""
                class="banner-image"
              />
            </a>
            <div class="ctrl-box">
              <i
                class="el-icon-close close-btn"
                v-show="flagGg1"
                @click="closeGg1()"
              ></i>
            </div>
          </div>
        </div>
        <div class="sidebar-block banner-block Gg2">
          <div
            class="banner banner sticky-banner"
            @mouseover="showGg2()"
            @mouseout="disshowGg2()"
          >
            <a
              href="https://juejin.cn/book/7117582869358182403?utm_source=web_banner&utm_medium=banner&utm_campaign=Book_zjk_0803"
            >
              <img
                src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a88a1ea956734105a5b002dfb48840cb~tplv-k3u1fbpfcp-no-mark:480:400:0:0.awebp?"
                alt=""
                class="banner-image"
              />
            </a>
            <div class="ctrl-box">
              <i
                class="el-icon-close close-btn"
                v-show="flagGg2"
                @click="closeGg2()"
              ></i>
            </div>
          </div>
        </div>

        <div
          class="sidebar-block app-download-sidebar-block sidebar-block shadow"
        >
          <div class="block-body">
            <a href="https://juejin.cn/app" class target="_blank">
              <div class="app-link">
                <img
                  src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/home.59780ae.png"
                  alt=""
                  class="qr-img"
                />
                <div class="content-box">
                  <div class="headline">下载稀土掘金APP</div>
                  <div class="desc">一个帮助开发者成长的社区</div>
                </div>
              </div>
            </a>
          </div>
        </div>
      </div> -->
      <div class="sidebar-block user-block">
        <div class="recommend-author-block sticky-authod-block">
          <header class="user-block-header">🎖️作者榜</header>
          <div class="user-list">
            <div class="item">
              <a
                href="https://juejin.cn/user/2305054774145918"
                class="link"
                target="_blank"
              >
                <img
                  src="https://p9-passport.byteacctimg.com/img/user-avatar/c01c52dcc59b98c1b026eb96f408329f~300x300.image"
                  alt="易师傅的头像"
                  class="lazy avatar avatar"
                  loading="lazy"
                />
                <div class="user-info">
                  <a
                    href="https://juejin.cn/user/2305054774145918"
                    target="_blank"
                    class="username username"
                  >
                    <span class="name" style="max-width: 128px">易师傅</span>
                    <span class="rank" blank="true">
                      <img
                        src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/lv-5.d08789d.png"
                        alt="lv-5"
                        title="创作等级"
                      />
                    </span>
                  </a>
                  <div class="position">前端搬砖师傅 @One Piece</div>
                </div>
              </a>
            </div>
            <div class="item">
              <a
                href="https://juejin.cn/user/554605767047053"
                class="link"
                target="_blank"
              >
                <img
                  src="https://p6-passport.byteacctimg.com/img/user-avatar/ddd95876f23c6e8ab56cab355f78a059~300x300.image"
                  alt="ShowMeAI的头像"
                  class="lazy avatar avatar"
                  loading="lazy"
                />
                <div class="user-info">
                  <a
                    href="https://juejin.cn/user/554605767047053"
                    target="_blank"
                    class="username username"
                  >
                    <span class="name" style="max-width: 128px">ShowMeAI</span>
                    <span class="rank" blank="true">
                      <img
                        src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/lv-5.d08789d.png"
                        alt="lv-5"
                        title="创作等级"
                      />
                    </span>
                  </a>
                  <div class="position">资深算法专家</div>
                </div>
              </a>
            </div>
            <div class="item">
              <a
                href="https://juejin.cn/user/3808363977648493"
                class="link"
                target="_blank"
              >
                <img
                  src="https://p6-passport.byteacctimg.com/img/user-avatar/6e8c293f951b44ce73ce7906de82686d~300x300.image"
                  alt="阿里云云原生的头像"
                  class="lazy avatar avatar"
                  loading="lazy"
                />
                <div class="user-info">
                  <a
                    href="https://juejin.cn/user/3808363977648493"
                    target="_blank"
                    class="username username"
                  >
                    <span class="name" style="max-width: 128px"
                      >阿里云云原生</span
                    >
                    <span class="rank" blank="true">
                      <img
                        src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/lv-6.b69935b.png"
                        alt="lv-6"
                        title="创作等级"
                      />
                    </span>
                  </a>
                  <div class="position">阿里云云原生公众号 @ 阿里巴巴集团</div>
                </div>
              </a>
            </div>
            <a
              href="https://juejin.cn/recommendation/authors/recommended"
              class="item"
              target="_blank"
            >
              <div class="more">
                <span>完整榜单</span>
                <i class="el-icon-arrow-right"></i>
              </div>
            </a>
          </div>
        </div>
      </div>
      <div class="sidebar-block link-block">
        <ul class="link-list">
          <li class="item">
            <a
              href="https://juejin.cn/book/6844733795329900551"
              class="link"
              target="_blank"
            >
              <img
                src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/juejin-tutu.d58819c.png"
                alt=""
                class="icon"
              />
              <span class="title">稀土掘金漫游指南</span>
            </a>
          </li>
          <li class="item">
            <a href="https://juejin.cn/extension" class="link" target="_blank">
              <img
                src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/juejin-extension-icon.4b79fb4.png"
                alt=""
                class="icon"
              />
              <span class="title">安装掘金浏览器插件</span>
            </a>
          </li>
          <li class="item">
            <a href="https://sourl.co/dQMLD9" class="link" target="_blank">
              <img
                src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/juejin-miner.b78347c.png"
                alt=""
                class="icon"
              />
              <span class="title">前往掘金翻译计划</span>
            </a>
          </li>
        </ul>
      </div>
      <div class="index-aside-footer" st:block="more">
        <ul class="more-list">
          <li class="item">
            <a href="https://juejin.cn/terms" target="_blank" rel="nofollow"
              >用户协议</a
            >
          </li>
          <li class="item">
            <a href="https://juejin.cn/license" target="_blank" rel="nofollow"
              >营业执照</a
            >
          </li>
          <li class="item">
            <a href="https://juejin.cn/privacy" target="_blank" rel="nofollow"
              >隐私政策</a
            >
          </li>
          <li class="item">
            <a href="https://juejin.cn/about" target="_blank" rel="nofollow"
              >关于我们</a
            >
          </li>
        </ul>
        <ul class="more-list">
          <li class="item">
            <a
              href="https://juejin.cn/map-author-A-1"
              target="_blank"
              rel="nofollow"
              >站点地图</a
            >
          </li>
          <li class="item">
            <a
              href="https://juejin.cn/book/6844733795329900551"
              target="_blank"
              rel="nofollow"
              >使用指南</a
            >
          </li>
          <li class="item">
            <a href="https://juejin.cn/links" target="_blank" rel="nofollow"
              >友情链接</a
            >
          </li>
          <li class="item">
            <a
              href="https://juejin.cn/more_posts"
              target="_blank"
              rel="nofollow"
              >更多文章</a
            >
          </li>
        </ul>
        <ul class="more-list">
          <li class="item">
            <a href="https://beian.miit.gov.cn/" target="_blank" rel="nofollow">
              京ICP备18012699号-3
            </a>
          </li>
        </ul>
        <ul class="more-list">
          <li class="item">
            <a
              href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010802026719"
              target="_blank"
              rel="nofollow"
            >
              <img
                src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/police.d0289dc.png"
                alt="police"
                style="vertical-align: middle"
              />
              京公网安备11010802026719号
            </a>
          </li>
          <li class="item">
            <span>版权所有：北京北比信息技术有限公司</span>
          </li>
          <li class="item">
            <span> 公司地址：北京市海淀区信息路甲28号13层B座13B-5 </span>
          </li>
          <li class="item">
            <span> 公司座机：010-83434395 </span>
          </li>
          <li class="item">
            <span>
              举报邮箱： <a href="mailto:feedback@xitu.io">feedback@xitu.io</a>
            </span>
          </li>
        </ul>
        <ul class="more-list">
          <li class="item">
            <a>©2022 稀土掘金</a>
          </li>
        </ul>
        <ul class="more-list account-list">
          <li class="item weibo">
            <a
              href="http://weibo.com/xitucircle"
              target="_blank"
              rel="nofollow nooperner noreferrer"
            >
              <img
                src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/weibo.0cd39f5.png"
                alt="微博"
                class="icon"
              />
            </a>
          </li>
          <li class="item wechat">
            <img
              src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/wechat.ce329e6.png"
              alt="微信"
              class="icon"
            />
            <div class="qr-panel">
              <div class="title">微信扫一扫</div>
              <img
                src="https://lf3-cdn-tos.bytescm.com/obj/static/xitu_juejin_web/img/juejin-qr.b247fde.jpeg"
                alt=""
                class="qr"
              />
            </div>
          </li>
        </ul>
      </div>
    </aside>
  </div>
</template>

<script>
export default {
  mounted() {
    window.addEventListener("scroll", this.watchScroll);
    this.getTime();
    this.changeWenhou();
  },
  data() {
    return {
      flagGg1: false,
      flagGg2: false,
      navBarFixed: false,
      sendTime: "",
    };
  },
  methods: {
    gotoNewview() {
      window.open(
        "https://juejin.cn/user/center/signin?from=main_page",
        "_blank"
      );
    },
    changeWenhou() {
      // console.log(this.sendTime);
      let wenhou = document.querySelector(".wenhou");
      if (this.sendTime >= 0 && this.sendTime < 12)
        wenhou.innerHTML = "上午好！";
      else if (this.sendTime >= 12 && this.sendTime < 14) {
        wenhou.innerHTML = "中午好！";
      } else if (this.sendTime >= 14 && this.sendTime < 18) {
        wenhou.innerHTML = "下午好！";
      } else {
        wenhou.innerHTML = "晚上好！";
      }
    },
    getTime() {
      const nowDate = new Date();
      // const date = {
      //     year: nowDate.getFullYear(),
      //     month: nowDate.getMonth() + 1,
      //     date: nowDate.getDate(),
      // }
      // const newmonth = date.month > 10 ? date.month : '0' + date.month
      // const day = date.date > 10 ? date.date : '0' + date.date
      this.sendTime = nowDate.getHours();
    }, //获取当前时间
    closeGg1() {
      let gg = document.querySelector(".Gg1");
      gg.style = "display:none";
    },
    closeGg2() {
      let gg = document.querySelector(".Gg2");
      gg.style = "display:none";
    },
    showGg1() {
      this.flagGg1 = true;
    },
    disshowGg1() {
      this.flagGg1 = false;
    },
    showGg2() {
      this.flagGg2 = true;
    },
    disshowGg2() {
      this.flagGg2 = false;
    },
    watchScroll() {
      let gg1 = document.querySelector(".yidong-block");
      var scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      //  当滚动超过 index-aside的高度 时，实现吸顶效果
      // 获取index-aside的高度 offsetHeight属性可以获取元素的可见高度值
      let heightH = this.$refs.init.offsetHeight;
      let heightT = this.$refs.T.offsetHeight;
      // console.log(heightT);
      let height = heightH;
      if (1054 >= heightH) height = heightH + heightT;
      else height = heightH;
      // console.log(height);
      // 超过height新增sticky-block类，实现吸顶

      if (scrollTop > height) {
        this.navBarFixed = true;
        gg1.classList.add("sticky-block");
      } else {
        this.navBarFixed = false;
        gg1.classList.remove("sticky-block");
      }
    },
  },
};
</script>

<style>
.banner .ctrl-box .close-btn:hover {
  opacity: 1;
}
.sidebar-block.sticky-block {
  position: fixed;
  background-color: transparent;
  box-shadow: none;
  /* opacity: 0; */
  transition: all 0.2s;
  width: 20rem;
  /* z-index: -1; */
  top: 67px;
  /* pointer-events: none; */
}
.aside {
  position: absolute;
  top: 0;
  right: 0%;
  /* display: flex; */
  /* width: 30%; */
}
.signin-tip {
  padding: 16px;
  background-color: #fff;
  box-sizing: border-box;
}
.index-aside .signin {
  width: 240px;
  height: 96px;
  margin-bottom: 16px;
}
.signin-tip .first-line {
  display: flex;
  justify-content: space-between;
  margin-bottom: 8px;
}
.signin-tip .first-line .icon-text {
  display: flex;
}
.signin-tip .first-line .title {
  margin-top: 2px;
  color: #1d2129;
  font-size: 18px;
  font-weight: 500;
}
.signin-tip .first-line .signin-btn {
  border: 1px solid #1e80ff;
  background-color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.signin-tip .first-line .signin-btn:hover {
  background-color: #e8f3ff;
  color: #388eff;
}
.signin-tip .first-line .btn {
  border-radius: 50px;
  height: 32px;
  width: 72px;
}
body {
  background-color: #f4f5f5;
}
.sidebar-block.banner-block {
  overflow: hidden;
}
.sidebar-block {
  background-color: #fff;
  box-shadow: 0 1px 2px 0 rgb(0 0 0 / 5%);
  border-radius: 2px;
  margin-bottom: 1.3rem;
  font-size: 1.16rem;
  line-height: 1.29;
  color: #333;
  width: 240px;
  /* aspect-ratio: auto 240/ 200; */
}
.sidebar-block.banner-block .banner {
  height: 200px;
}
.banner {
  aspect-ratio: auto 240/ 200;
  position: relative;
  font-size: 0;
  cursor: pointer;
}

.banner .banner-image {
  width: 100%;
  height: 100%;
}
img {
  border-style: none;
}
a {
  text-decoration: none;
  cursor: pointer;
  color: #909090;
}

.app-link {
  display: flex;
  align-items: center;
  padding: 1rem;
}
.qr-img {
  margin-right: 16px;
  width: 4.167rem;
  height: 4.167rem;
}
.headline {
  font-weight: 500;
  font-size: 14px;
  line-height: 22px;
  color: #1d2129;
}
.desc {
  margin-top: 0.5rem;
  font-size: 12px;
  line-height: 20px;
  color: #86909c;
}

.recommend-author-block .item .link .user-info {
  overflow: hidden;
}
.rank img {
  width: 35px;
  height: 16px;
}
.rank {
  display: inline-flex;
  align-items: center;
  margin-left: 0.33rem;
  /* vertical-align: middle; */
  /* 1.该属性定义行内元素的基线相对于该元素所在行的基线的垂直对齐。 */
  /* 2.vertical-align:middle是将元素盒子的垂直中点和父盒子的baseline加上父盒子的x-height的一半对齐。(注意字母x的关键作用) */
  vertical-align: middle;
}
.recommend-author-block .item .link .username {
  font-size: 1.16rem;
  font-weight: 400;
  color: #333;
  white-space: nowrap;
  /* 清除浮动 */
  overflow: hidden;

  /* 默认值:clip;
适用于:所有元素
clip:当前对象内文本溢出时不显示省略标记(...),而是将溢出部分裁剪。
ellipsis:当对象内文本一处时显示省略标记(...)。
当然这还是不够的，需要加点调料才能出现效果:
那就是配合
overflow:hidden
white-space:overflow; */
  text-overflow: ellipsis;
  margin-bottom: 3px;
}
.recommend-author-block .item .link .description,
.recommend-author-block .item .link .position {
  color: #909090;
  font-size: 1rem;
  margin-bottom: 3px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.username {
  font-size: 1.25rem;
  font-weight: 600;
  color: #2e3135;
  display: flex;
  align-items: center;
}
.recommend-author-block .item .link .user-info {
  overflow: hidden;
}
.recommend-author-block .item .link .avatar {
  flex: 0 0 auto;
  width: 3.8rem;
  height: 3.8rem;
  /* 使边框变成圆形 */
  border-radius: 50%;
  margin-right: 0.5rem;
}
.recommend-author-block .item .link {
  padding: 1rem 1.3rem;
  display: flex;
  align-items: center;
  cursor: pointer;
}
.recommend-author-block .user-block-header {
  padding: 1rem 1.3rem;
  border-bottom: 1px solid hsla(0, 0%, 59.2%, 0.1);
}

element.style {
  max-width: 128px;
}

.username .name {
  display: inline-block;
  vertical-align: top;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
html {
  font-size: 12px;
  /* 使容器自动换行 */
  word-break: break-word;
  /* 浏览器在绘制文本时将着重考虑易读性，而不是渲染速度和几何精度.它会使字间距和连字有效。该属性值在移动设备上会造成比较明显的性能问题。 */
  text-rendering: optimizeLegibility;
  color: #333;
  background-color: #f4f5f5;
}
.item :hover {
  background-color: #fbfbfb;
}
.recommend-author-block .item .more {
  color: #007fff;
  padding: 1rem 0;
  text-align: center;
  border-top: 1px solid hsla(0, 0%, 59.2%, 0.1);
}
.recommend-author-block .item .more .icon {
  margin-left: 5px;
}
.sidebar-block.link-block .item {
  position: relative;
}
.sidebar-block.link-block .link {
  display: flex;
  align-items: center;
  padding: 1rem;
  height: 100%;
}
.sidebar-block.link-block .icon {
  width: 3rem;
  margin-right: 0.8rem;
}
.sidebar-block.link-block .title {
  position: relative;
  font-size: 1.16rem;
  line-height: 1;
  color: #333;
}
.sidebar-block li {
  list-style: none;
}
li {
  list-style: none;
  display: list-item;
  text-align: -webkit-match-parent;
}
.sidebar-block.link-block .link-list {
  padding: 0;
}
.index-aside-footer .more-list {
  font-size: 1rem;
  line-height: 1.6;
  color: #9aa3ab;
}
.index-aside-footer .more-list .item {
  float: left;
}
.sidebar-block.link-block .link-list {
  padding: 0;
}
a,
button,
input {
  margin: initial;
  margin-right: 5px;
}

.index-aside-footer {
  background-color: transparent;
  box-shadow: none;
}
.index-aside-footer ul {
  list-style-type: disc;
  padding: 0;
  margin: 0;

  /* 使用float之后需要清除浮动，否则父元素的高度为0，产生高度塌陷。 */
  overflow: hidden;
}
.more-list a:hover {
  color: #007fff;
}

.index-aside-footer .more-list .item:not(:last-child):after {
  content: "";
  margin-right: 8px;
}
.index-aside-footer .more-list:after {
  display: table;
  content: "";
  clear: both;
}
.index-aside-footer .more-list.account-list {
  display: flex;
  justify-content: flex-start;
  margin: 1rem 0;
}
.index-aside-footer .more-list .item {
  float: left;
}
.index-aside-footer .more-list.account-list .icon {
  width: 24px;
  cursor: pointer;
}
.index-aside-footer .more-list.account-list .wechat .qr-panel {
  /* position: absolute; */
  background: #fff;
  width: 10rem;
  top: 100%;
  left: -100%;
  z-index: 2;
  padding: 0.8rem 0 0;
  opacity: 0;
  border: 1px solid #ddd;
  transform: translate(-24px);
}
.index-aside-footer .more-list.account-list .wechat .title {
  text-align: center;
}
.index-aside-footer .more-list.account-list .wechat {
  position: relative;
}
.index-aside-footer .more-list.account-list .wechat .qr {
  width: 100%;
}

.index-aside-footer .more-list.account-list .icon:hover + .qr-panel {
  opacity: 1 !important;
}

.banner .ctrl-box .close-btn {
  position: absolute;
  top: 0.5rem;
  right: 0.5rem;
  font-size: 1.5rem;
  color: #909090;
  opacity: 0.5;
  /* display: none; */
}
.banner .ctrl-box .close-btn:hover {
  opacity: 1;
}
</style>