---

layout: default
title: Jekyll

---

# Jekyll

是一個static site generator, 可以幫我們把各種形式的markup(txt, MarkDown等)轉換成HTML，並且自動生成，自動update到網站上。好像還可以自動生成目錄，幫助鳥瞰網站內容。

大部分的內容都可以在Jekyll的step by step tutorial找到。

<https://jekyllrb.com/docs/step-by-step/01-setup/>



安裝通常在Unix系統下，因此我必須用cygwin.

Jekyll的安裝與gem和bundler兩個tool關係密切。在林克融<http://sayaku.github.io/blog/2016/05/05/rubyde-rvm-gem-bundler/>的文章[筆記]Ruby的RVM,GEM,Bundler是什麼？寫得清楚，gem是用來搜尋跟管理封包的tool. 例如用

```
`    $ gem install bundler `
```

可以安裝bundler.

bundler是用來解決封包相依性的問題。用

```bash
`    $ gem install bundler`
```

可以在目錄下建立一個Gemfile，可以在裡面聲明要用的套件以及版本。

創好一個資料夾以及index.html後，切換到此資料夾並且

```bash
$ jekyll serve
```

此指令做兩件事: 1. 建造網站並且將之放到_site資料夾。 2. 若修改內容文件，會定時update網站。執行畫面如下:

![1591501900743](C:\Users\user\AppData\Roaming\Typora\typora-user-images\1591501900743.png)

進到http://localhost:4000就可以看到Hello World!

一旦有所更動，馬上就出現

![1591502174924](C:\Users\user\AppData\Roaming\Typora\typora-user-images\1591502174924.png)

## Liquid

此乃一個templating language，就是可以用來建立網站的template.

要使用liquid時，至少要在html的最上面加上

![1591502436582](C:\Users\user\AppData\Roaming\Typora\typora-user-images\1591502436582.png) 

# Layouts

Layout就是頁面的template. 其被存在\_layouts/default.html

## Deployment

最後的發布用

```
JEKYLL_ENV=production bundle exec jekyll build
```

可以將生成的_site資料夾放到server(如Google Drive)，就可以線上觀看。