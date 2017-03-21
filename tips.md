* git clone下仓库，task0003里还没有js文件夹.首先cd到ife-2015spring，git init
   然后cd到task0003，git init
   然后建文件夹，index.js放进去
       git add js
   git commit
   最后
       git add task0003/js
   git commit
git push
或者直接新建文件夹，粘贴文件，然后
git add task0003/js
git commit
git push

* 在网页版github中修改了用于显示demo的主目录index.html后，在本地应该要git pull 一次
然后才能git push

* 远程库克隆，然后cd到repo,git init，操作repo里的子文件夹时，要先cd到子文件夹路径，然后git init，之后在操作子文件夹，然后在子文件夹下git commit，cd 到repo，再进行git add/rm，git commit，然后再git push
