*   查找 `.git` 文件
    
    ```
    find . -name '.git'
    ```
   
*   查找删除 `.git` 文件

    ```
    find . -name '.git' | xargs rm -Rf
    ```     
*  关联仓库
    
    ```
    git init
    git add .
    git commit -m "first commit"
    git remote add origin `url`
    git push -u origin master
    ```
