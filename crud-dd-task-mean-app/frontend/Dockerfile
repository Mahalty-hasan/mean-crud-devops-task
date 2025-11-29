# STEP 1 — Build Angular App
FROM node:18-alpine AS build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# Build Angular for production
RUN npm run build --prod

# STEP 2 — Serve using nginx
FROM nginx:stable-alpine

# Copy build output to nginx html folder
COPY --from=build /app/dist/ /usr/share/nginx/html/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
