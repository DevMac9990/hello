1. 创建空仓库  
2. 下载到本地  
    - `git clone git@gitee.com:Cauchy_AQ/hello.git`  
3. hello 项目目录下初始化，设置项目路径  
    - `go mod init gitee.com/Cauchy_AQ/hello`  
4. 创建编写 hello.go 文件，对外提供方法 SayHello()  
5. 项目代码 push 到远端 master 分支  
    - `git add .`  
    - `git commit -m "SayHello() v0.1.0"`  
    - `git push origin master`  
6. 为代码包打上标签  
    - `git tag -a v0.1.0 -m "release version v0.1.0"`   
7. 项目代码 push 到远端标签分支  
    - `git push origin v0.1.0`  
8. 迭代版本，go.mod 修改当前包的引入路径  
    - `module gitee.com/Cauchy_AQ/hello/v2`
    - `git add .`
    - `git commit -m "SayHello(string) v2.0.0"`
    - `git push`
    - `git tag -a v2.0.0 -m "release version v2.0.0"`
    - `git push origin v2.0.0`


9. 项目使用发布的包  
    - 设置 GOPRIVATE

        - `go env -v GOPRIVATE=gitee.com`


    - 项目导入包
        - `go get gitee.com/Cauchy_AQ/hello/v2@v2.0.0`
        - `go mod tidy`
    
    
10. 补充

    - `git tag -l`  
    - `git show v1.0.0`  
    - `git push origin --delete v1.0.0`  