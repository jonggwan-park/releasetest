# Node.js 환경 설정
FROM node:18 AS build

# 작업 디렉토리 설정
WORKDIR /app

# package.json 및 package-lock.json 복사 후 의존성 설치
COPY frontend/package.json frontend/package-lock.json ./
RUN npm install --force


# 프로젝트 코드 복사
COPY frontend/. .
RUN npm run build
# 개발 서버 실행 (파일 변경 시 자동 반영됨)




# Nginx 설정

FROM nginx:latest

COPY nginx/nginx.conf /etc/nginx/nginx.conf

COPY --from=build /app/build /usr/share/nginx/html



CMD ["nginx", "-g", "daemon off;"]

