FROM node:20-alpine

WORKDIR /app

# Copiar solo package files primero (aprovecha caché de Docker)
COPY package*.json ./

# Instalar dependencias
RUN npm ci

# Copiar el resto del código
COPY . .

# Build
RUN npm run build

EXPOSE 9000

CMD ["npm", "run", "start"]
