# Usar uma imagem base mínima do Go
FROM golang:alpine

# Definir o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copiar o código fonte para o diretório de trabalho
COPY . .

# Compilar o código
RUN go build -o app

# Configurar a imagem base final
FROM scratch

# Copiar o binário compilado do estágio anterior
COPY --from=0 /app/app /app/app

# Definir o comando padrão a ser executado quando o contêiner for iniciado
CMD ["/app/app"]