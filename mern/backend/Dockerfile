FROM node:18-alpine AS build
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
RUN npm run build
FROM node:18-alpine AS runtime
WORKDIR /app
COPY --from=build /app .
EXPOSE 5050
CMD ["npm", "start"]