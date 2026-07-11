# Messenger — 本地镜像

这是对已获授权的 `https://messenger.abeto.co/` 前端体验做的本地静态镜像：WebGL 场景、标题动画、Begin 入口、鼠标/触控相机、键盘控制、音频、图标和场景资源都已经放在本目录的 `assets/` 下。

## 启动

```bash
python3 -m http.server 4173
```

然后打开 <http://127.0.0.1:4173/>。

必须通过 HTTP 服务访问，直接双击 `index.html` 会被浏览器的模块和 Worker 安全策略拦截。

## 说明

- `assets/App3D-DwM1eiaC.js`、Worker、字体、纹理、Draco/KTX2 解码器和 3D 几何资源均为本地文件，启动时不需要从目标站点下载前端资源。
- 原站的多人房间服务地址仍由原始客户端保留（`wss://multiplayer-server-76608060529.us-central1.run.app`）。因此多人同步依赖该服务；若要完全自托管，需要替换客户端中的 WebSocket 服务并实现原站协议。
- 目标站点的授权由使用者提供；本目录仅用于该授权范围内的本地开发和部署。
