# Projeto final - CI/CD

> - *Curso*: DevOps
> - *Módulo*: Pipelines de CI e CD
> - *Professora*: Talita

## Enunciado

- Construir uma imagem Docker dentro de um processo de CI/CD, utilizando Jenkins em 2 branches (development e main). 
- Realizar o versionamento do código e das imagens Docker, utilizando GitHub como repositório.
- Usar o Dockerfile no repositório: https://github.com/Talits/ada-ci 
- Exemplo Jenkinsfile: https://github.com/Talits/Jenkinsfile-projetoFinal/blob/main/Jenkinsfile

## Passos para execução

- [X] Instalar o java
- [X] Subir o agent através da configuração de node
  - [X] Criar novo nó
  - [X] Agent permamente
  - [X] Diretório de raiz remoto .
  - [X] Criar agent
- [X] Jenkinsfile → nome do nó configurado
- [X] Configurar plugin Docker e credenciais Dockerhub
