# Use uma imagem base para Ruby 2.7.7 com Alpine para uma configuração leve e controlada
FROM ruby:2.7.7-alpine

# Instala as dependências do sistema necessárias
RUN apk update
RUN apk add --no-cache \
  postgresql-dev \
  sqlite-dev \
  build-base \
  yaml \
  tzdata \
  bash

# Define o diretório de trabalho
WORKDIR /app

# Copia o Gemfile para o container
COPY Gemfile* ./

# Instala as gems
RUN gem install bundler -v 2.4.22
RUN gem install io-console
RUN bundle install

# Copia o restante dos arquivos da aplicação para o container
COPY . .

# Expõe a porta do servidor Rails
EXPOSE 3000

# Comando para iniciar o servidor Rails
CMD ["bash", "entrypoint.sh"]