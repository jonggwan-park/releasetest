FROM nginx:latest

# Nginx 설정 파일 복사
COPY nginx/nginx.conf /etc/nginx/nginx.conf

# 정적 파일 복사
COPY --from=frontend /app/build /usr/share/nginx/html

CMD ["nginx", "-g", "daemon off;"]
