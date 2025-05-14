FROM node:20-alpine

WORKDIR /app

ENV HOST 0.0.0.0

# 複製 package.json 與 lock 檔
COPY package*.json ./

# 安裝依賴
RUN npm install

# 複製所有檔案到容器中
COPY . .
RUN npm run build

# 安裝 serve 套件來提供靜態檔案
RUN npm install -g serve

# 對外開放的 port（預設是 8080）
EXPOSE 8080

# 啟動開發伺服器，--host 0.0.0.0 是為了使伺服器可以從容器外部（主機）訪問。
CMD ["serve", "-s", "dist", "-l", "8080"]