# Kube Manifest Studio

Kubernetes YAML 清单和 kubectl 命令生成器。纯 HTML、CSS 和 JavaScript，入口文件为 `dist/index.html`。

支持 Deployment、ReplicaSet、StatefulSet、DaemonSet、Job、CronJob，配套 Service，以及 emptyDir、ConfigMap、PVC、静态 NFS/本地 PV 和 StatefulSet PVC 模板。生成结果包含对齐的中文字段注释，支持复制和下载。

## 在其他电脑上使用

```sh
git clone https://github.com/lswhere/kube-manifest-studio.git
cd kube-manifest-studio
```

用浏览器打开 `dist/index.html` 即可使用。也可以在已安装 Python 的电脑上运行本地 HTTP 服务。

```sh
python -m http.server 8080 --directory dist
```

然后访问 http://localhost:8080 。

更新本地源码时，在项目目录执行 `git pull`。

## 部署

将 `dist` 目录作为静态网站根目录。`.openai/hosting.json` 包含当前 Sites 项目的关联配置。

页面在浏览器中生成文本。请在终端运行输出的 kubectl 命令。应用清单前需准备好命名空间、被引用的 ConfigMap/PVC 和底层存储。

已验证清单生成逻辑，实际部署取决于集群版本、权限和存储环境。
