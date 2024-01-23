# Taurus.RegistryCenter is a microservice registry center for asp.net or asp.net core.
<h3>【 <a href='./README.md'>中文</a> | <a href='./README_en.md'>English</a>】</h3>
<hr />
# Taurus.RegistryCenter 微服注册中心，使用 .Net Core 示例：
<h4>1、在 Docker 中拉取镜像直接运行：</h4>
<p>下载镜像，当前【2024-01-23 发布的版本是3.3.0.1】：</p>
<pre><code>docker pull registry.cn-hangzhou.aliyuncs.com/taurus-netcore/taurus.registrycenter:3.3.0.1</code></pre>
<p>运行容器，映射对外使用80和443端口【默认镜像中的应用打包运行的监听端口为：8080 和 443】：</p>
<pre><code>docker run -d -p 80:8080 -p 443:443 --name=rc --security-opt seccomp=unconfined registrycenter</code></pre>

<h4>2、打开工程文件，运行 src 目录下程序：</h4>
<p>默认运行环境是当前最新的 .net core 8 版本，程序主要依赖Taurus.Mvc的Nuget包。</p>
<p>可以根据需要自行创建工程文件，引用Taurus.Mvc的Nuget包即可，该包支持.net 和 .net core 几乎所有版本。</p>

<h4>3、程序启动正常时：</h4>
<p>默认主页显示为：404，没有可显示页面，需要手动输入以下网址进入后台：/admin/login</p>
<p>默认账号：admin，密码空，直接点登陆即可进入后台。</p>
<p><img src="https://img2023.cnblogs.com/blog/17408/202306/17408-20230606151806482-635586726.png" alt="" loading="lazy" class="medium-zoom-image"></p>

<h4>4、其它说明：</h4>
<p>程序启动后，注册中心即运行成功，不需要其它配置，等待微服务网关、注册中心（从）、或客户端链接上即可。</p>
<p>程序的自身的访问Url，需要保障其它微服务端可以访问。</p>
<p>后续可以在/admin/index 中查看连接上的客户端。</p>
<p><img src="https://img2023.cnblogs.com/blog/17408/202306/17408-20230606152004338-2079864972.png" alt="" loading="lazy" class="medium-zoom-image"></p>

<h4>5、注册中心（从）启用：</h4>
<p>为了保障注册中心的高可用，可以启动注册中心（从）。</p>
<p>启动注册中心（从）的步骤，和启动注册中心一致，仅在启动完后，需要进入管理后台，配置增加指向注册中心的链接</p>
<p>配置项为：MicroService.Server.RcUrl，界面配置始下：</p>
<p><img src="https://img2024.cnblogs.com/blog/17408/202401/17408-20240123173032033-311040766.png" alt="" loading="lazy" /></p>
<p></p>
