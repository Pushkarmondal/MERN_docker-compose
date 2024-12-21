FROM node:18-alpine AS build
WORKDIR /app
COPY package.json  package-lock.json ./
RUN npm install
COPY . .
FROM node:18-alpine AS runtime
WORKDIR /app
COPY --from=build /app .
EXPOSE 5173
CMD ["npm", "run", "dev"]