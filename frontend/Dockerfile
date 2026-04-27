FROM node:18
WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm ci

COPY . .
RUN npm run build
#RUN npm install --global http-server

#CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]

# Копируем билд в volume при старте контейнера
#CMD cp -r /app/build/. /static/ && echo "Frontend build copied to static volume"
#CMD sh -c "cp -r /app/build/. /static/ && tail -f /dev/null"
CMD sh -c "cp -r /app/build/. /frontend/ && tail -f /dev/null"
