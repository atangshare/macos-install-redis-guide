# macOS安装Redis完整指南

## 方法一：使用Homebrew安装

### 1. 使用Homebrew安装Redis

```bash
brew install redis
```

### 2. 启动Redis服务

```bash
redis-server

# 如果想每次开机自动启动Redis服务
brew services start redis
```

### 3. 验证安装

```bash
redis-cli ping
```
如果返回"PONG"，说明Redis安装成功并正常运行。


## 方法二：Docker安装

新建一个`docker-compose.yml`

```yml
services:
  redis:
    image: redis
    ports:
      - "6379:6379"
    volumes:
      - redis_data:/data
volumes:
  redis_data:
```

运行`docker compose up -d`。


