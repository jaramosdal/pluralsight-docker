# Test web app that returns the name of the host/pod/container servicing req
# Linux x64
FROM node:current-alpine

LABEL org.opencontainers.image.title="Hello Docker Learners!" \
      org.opencontainers.image.description="Web server showing host that responded" \
      org.opencontainers.image.authors="@nigelpoulton"

# Create directory in container image for app code
# . = todos los archivos y subdirectorios del lugar desde el que ejecutamos docker build
RUN mkdir -p /usr/src/app

# Copy app code (.) to /usr/src/app in container image
COPY . /usr/src/app

# Set working directory context
WORKDIR /usr/src/app

# Install dependencies from packages.json
RUN npm install

# Command for container to execute
# Comando a correr siempre que un contenedor se lance desde esta imagen
ENTRYPOINT [ "node", "app.js" ]


# docker image build -t jaramosdal/gsd:first-ctr .
# =, ya que image es opcional
# docker build -t jaramosdal/gsd:first-ctr .

# Publicar a repositorio (en este caso, Docker Hub)
# docker image push jaramosdal/gsd:first-ctr

# Borrado de una imagen local
# docker image rm jaramosdal/gsd:first-ctr

# Correr una imagen local o remota (si es remota, primero se descarga)
# -d = Correr el contenedor en sugndo plano, no vinculado a este terminal
# docker container run -d --name web -p 8000:8080 jaramosdal/gsd:first-ctr