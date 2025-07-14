# rules-template

- **订阅转换模板**

  - 平时使用代理配置时候会将规则写入本地软件配置里。会出现一些问题。例如，不同客户端无法共用分流规则（singbox的分流配置无法放到clash中使用），修改一个客户端无法同步另外一个客户端，（修改手机singbox分流规则。PC的clash无法同步）等问题。为了解决这类问题，可以写一份分流规则模板放代码托管平台托管。然后配合订阅转换服务将模板转换成不同客户端的配置。

- 订阅转换服务安装：

  - 参考文档：

    - [https://github.com/tindy2013/subconverter]: 	"支持clash ss ssr V2Ray等客户端转换"
      [https://github.com/asdlokj1qpi233/subconverter]: 	"推荐！在前一个转换服务的基础上添加singbox，Surge 5的支持"

  - ```
    
    ```

    

- 下面以openwrt的clash为例：

  - 订阅转换部署：

    ​	使用dockers：

    ```
    docker run --name=subconverter -d --restart=unless-stopped --memory=1024m -e TZ=Asia/Shanghai -p 25500:25500 asdlokj1qpi23/subconverter:latest
    ```

       部署成功后访问 http://主机IP:端口/version   ，如果有出现版本号表示部署成功。

      订阅转换服务器转换地址为：http://主机IP:端口/sub 

  - 先fork一份本项目，进入到fork的项目后进入自己项目里开始编辑clash_rules.ini文件，将绿色下划线替换成自己github的用户名，来指向自己仓库的规则。

    - ![image-20250501151015476](image-20250501151015476.png)

  - 点击软路由openclash插件，进入到订阅配置中

  - ![image-20250501151206283](image-20250501151206283.png)

  - 新建一个配置

  - 获取配置只读地址：

  - ![image-20250501151625443](image-20250501151625443.png)

    - 点击raw打开后跳转一个新标签。复制标签地址
    - ![image-20250501151714402](image-20250501151714402.png)

  - 修改配置：

    - ![image-20250501152138844](image-20250501152138844.png)

      ​	保存配置。并且应用配置就生效了

    