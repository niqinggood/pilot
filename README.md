# Pilot 系统部署指南

saddle**.whl 是python的模块，需要先安装
pip install saddle*.whl

pilot 是一款轻量级MLOps，采用前后端分离架构：
## 目录结构
pilot/
├── go_backend.exe # 后台主程序
├── build/ # 前端编译文件目录
└── config/ # 系统配置文件目录

## 快速启动

### 后台服务启动
1. **默认端口启动**  
   直接双击 `go_backend.exe` 或执行：
   ```bash
   ./go_backend.exe

   默认监听端口：5000
2.自定义端口
   ./go_backend.exe -port [端口号]
   ./go_backend.exe -port 5001

若build前端，采用nginx部署,前端和后台服务ip不一致时，需要在build目录下修改config.json里的{"apiBaseUrl": "http://localhost:5000" }中的localhost:5000改为实际后台地址
