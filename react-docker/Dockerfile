FROM node:20-alpine

WORKDIR /app

# 複製 package.json 與 lock 檔
COPY package*.json ./

# 安裝依賴
RUN npm install

# 複製所有檔案到容器中
COPY . .

# 對外開放的 port（預設是 5173）
EXPOSE 5173

# 啟動開發伺服器，--host 0.0.0.0 是為了使伺服器可以從容器外部（主機）訪問。
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]