# zhucpa.ca — MarkhamCPA 静态网站

Wix 原站的静态重建版, 可直接部署到 GitHub Pages (免费托管), 域名保持 zhucpa.ca 不变。

## 文件清单

```
CNAME                    自定义域名 (zhucpa.ca)
index.html               首页 (中文)
about.html               关于 Andy Zhu (中文)
contact.html             联系我们 + 预约 (中文)
blog/index.html          税务博客索引 (中文)
blog/post-1.html         为什么高收入的人群热衷慈善捐款 (2020-12-28)
blog/post-2.html         由于低利率变更房屋贷款的银行罚金能不能作为租房费用? (2020-11-09)
blog/post-3.html         全面解析非税务居民的“清税证明” (2020-11-06)
blog/post-4.html         PREC安省个人地产公司有关TOSI税务思考 (2020-10-06)
blog/post-5.html         PREC安省个人地产有限公司的⑩问答 (2020-10-04)
en/index.html            首页 (英文)
en/about.html            About Andy Zhu (英文)
en/contact.html          Contact + 预约 (英文)
en/blog/index.html       Tax Blog 索引 (英文导航, 文章正文为中文原文)
en/blog/post-1..5.html   同上 5 篇文章 (英文导航, 中文正文)
assets/style.css         全站样式 (深蓝 + 白, 移动端适配)
assets/*.jpg / *.png     本地图片 (见下)
```

图片 (全部本地引用, 不热链 Wix):
- hero-home.jpg — 首页主图 (写财务图表的人, 深蓝底)
- cpa-ontario.png — CPA Ontario 标志
- portrait.jpg — Andy Zhu 正装肖像 (已压缩至约 100KB)
- wechat-qr.jpg — 微信二维码
- post1-cover.jpg / post1-receipt.jpg — 文章 1 配图
- post2-cover.jpg — 文章 2 配图
- post3-cover.jpg / post3-t2062.png / post3-t2062a.png — 文章 3 配图
- post4-cover.jpg — 文章 4 配图
- post5-cover.jpg — 文章 5 配图

未收录的图片 (原站禁止直接下载, HTTP 403, 已用纯色深蓝设计替代, 无破图):
- 关于页与联系页的 hero 背景图、联系页服务配图
- 文章 3 情况 2 中的两张 T2062/T2062A 表格截图 (正文已保留, 图片位置有注释说明)

## 部署到 GitHub Pages (免费)

1. 在 GitHub 新建一个公开仓库, 例如 `zhucpa-ca` (名字任意)。
2. 把本文件夹的全部内容上传到仓库根目录 (不要多套一层文件夹)。
   - 命令行: `git init && git add . && git commit -m "MarkhamCPA site" && git branch -M main && git remote add origin https://github.com/<你的用户名>/zhucpa-ca.git && git push -u origin main`
   - 或直接在 GitHub 网页端用 "Add file → Upload files" 上传。
3. 打开仓库 Settings → Pages: Source 选 "Deploy from a branch", Branch 选 `main` / `(root)`, 保存。
4. 等一两分钟, 站点即在 `https://<你的用户名>.github.io/zhucpa-ca/` 上线。

## 接入自定义域名 zhucpa.ca (域名在 NameSilo)

`CNAME` 文件里已写好 `zhucpa.ca`, GitHub Pages 会自动读取。

在 NameSilo 的域名 DNS 设置里, 删除旧的 Wix 相关记录, 改为:
- 4 条 A 记录, 主机名 `@`, 指向 GitHub Pages 的 IP:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`
- 1 条 CNAME 记录, 主机名 `www`, 指向 `<你的用户名>.github.io` (末尾带一个点, 按 NameSilo 的要求填)。

DNS 生效需要几分钟到几小时。生效后在仓库 Settings → Pages 里勾选 "Enforce HTTPS"。

注意: 改 DNS 之前, 先确认 Wix 订阅已取消或不再续费, 避免两边同时扣费。切过去之后 Wix 站点即停止服务, 新站接管 zhucpa.ca。

## 预约功能

联系页的“预约 15 分钟咨询”目前显示电话 / 邮箱 / 微信, 预约按钮是隐藏的。
去 Calendly (免费版) 建一个 15 分钟活动, 把链接填进 `contact.html` 和 `en/contact.html` 文件顶部的注释和 `<script>` 里的 `CALENDLY_URL` 常量 (两处保持一致), 按钮就会自动出现。

## 内容说明

- 博客文章为原站中文原文, 包括原文的笔误和数字写法 (如 "Accoutant"、"22,800"、帖 2 中的 "2011/2012" 年份), 未做修改。
- 站点没有服务介绍、团队成员、地址、营业时间 —— 原站也没有这些内容, 故未添加。
- 已删除的第 6 篇博客 ("报税新福利: 加拿大政府每年 250 刀的职业金", live 页 404) 未收录。
