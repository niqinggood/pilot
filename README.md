
# Pilot 系统部署指南

## 🛠️ 环境准备
需先安装 Python 依赖：
```bash
pip install saddle*.whl


📂 目录结构
#pilot 是一款轻量级MLOps，采用前后端分离架构：
pilot/
├── go_backend.exe    # 后端主程序
├── build/            # 前端编译文件
│   └── config.json   # 前端配置文件
└── config/           # 系统配置目录
前端采用react,后台采用go，
🚀 快速启动

### 后台服务启动
1. **默认端口启动**  
   直接双击 `go_backend.exe` 或执行：
   ```bash
   ./go_backend.exe

   默认监听端口：5000
2.自定义端口
   ./go_backend.exe -port [端口号]
   ./go_backend.exe -port 5001

##nginx前端部署
修改 API 地址：

bash

### 编辑 build/config.json
{
  "apiBaseUrl": "http://实际后台IP:端口" 
}
Nginx 配置示例：


server {
    listen       80;
    server_name  your.domain.com;
    
    location / {
        root   /path/to/build;
        index  index.html;
    }
}
