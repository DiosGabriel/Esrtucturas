# Etapa 1: build y entorno de desarrollo
FROM node:18

# Establece el directorio de trabajo
WORKDIR /app

# Copia los archivos del proyecto
COPY package*.json tsconfig*.json ./
COPY src ./src

# Instala dependencias
ENV npm_config_unsafe_perm=true
RUN npm install -g esbuild
RUN npm install

# Compila TypeScript a JS (asegúrate de tener "outDir": "dist" en tsconfig.json)
RUN npx tsc

# Expone el puerto donde corre tu API (asegúrate que coincide con tu app, p.ej., 3001)
EXPOSE 3002

# Comando para desarrollo (puedes cambiar por otro si usas build separado)
CMD ["node", "dist/index.js"]
