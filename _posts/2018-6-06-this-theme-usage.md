---
toc: true 

title:  "About Minimal Mistakes Quick-Start Guide"

tag:
  - Minimal-Mistakes-Usage

---

* 此 `jekyll` 博客主题 `Minimal Mistakes` 项目下的静态文件，会自动打包到 `_site` 目录下，`assets 和 _pages` 正是这样被打包的。食用时，尽量用统一的文件夹存放静态资源，以使根目录保持整洁。


## 页面头部生成目录
* 长篇文章需要一个目录导航，`Minimal Mistakes` 主题提供了这个功能
* 使用 `<h2> 和 <h3>` 的标签，即 `##` `###` 这两个语法生成目录

## 本主题使用规范
* 系列类型的文章，才在页头使用 `categories`
* 大杂烩类文章，添加 `tag` 就好，每篇文章都使用分类和标签，会增加不必要的重复
* 虽然每篇文章 `categories` 和 `tag` 都可以添加多个，但一般只添加一个就好
* `tag` 的多个单词使用短横线-链接， `categories` 则正常书写
* `_posts` 目录下的文件名的日期若超出当前日期，则文章不会输出，除非修改到 “今天至过去” 的日期
* 标签、分类名称尽量简短

