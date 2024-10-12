# Use uma imagem base para Node.js compatível com Vite
FROM node:18

# Define o diretório de trabalho
WORKDIR /app

# Copia os arquivos de dependências para o container
COPY package*.json ./

# Instala as dependências do projeto
RUN npm install

# Copia o restante dos arquivos da aplicação para o container
COPY . .

# Executa a build do projeto para produção
RUN npm run build

# Expõe a porta onde a aplicação irá rodar
EXPOSE 4173

# Comando para iniciar o servidor de preview do Vite
CMD ["npm", "run", "preview"]
