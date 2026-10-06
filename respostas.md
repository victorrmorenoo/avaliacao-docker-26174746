# Respostas · Avaliação Prática de Docker · ViaSerra Transportes (Turma C)

**Nome:** Victor Moreno Barbara  
**Matrícula:** 26174746  
**Usuário do GitHub:** victorrmorenoo  
**Usuário do Docker Hub:** victoormorenoo  

Responda com as suas palavras e com o que aconteceu na SUA máquina. Resposta curta e certa vale mais
do que texto longo copiado. Resposta que contradiz o seu próprio Dockerfile vale zero.

## Parte 1 · Dockerfile do portal

1. Qual imagem base você usou e qual o tamanho final da imagem do portal (saída de `docker images`)?  
- Utilizei a imagem `nginx:1.27-alpine`, o tamanho final da imagem foi de 21MB

2. Em qual pasta do container o Nginx procura os arquivos do site? Mostre o comando que você usou para
   conferir que o `index.html` está lá dentro.  
- O nginx procura os arquivos na pasta usr/share/nginx/html, o comando que utilizei foi `gdocker exec -it teste-portal sh`, depois dentro do terminal do container usei o `ls` para listar todos os arquivos da pasta


## Parte 2 · Docker Hub

3. Nome completo da imagem publicada e link público do repositório no Docker Hub.
- **Nome completo da imagem:** victoormorenoo/viaserra-portal:1.0-26174746
- **Link Público:** https://hub.docker.com/r/victoormorenoo/viaserra-portal

4. Se você mudar o HTML, quais comandos precisa rodar para que a versão nova chegue ao Docker Hub?

## Parte 3 · Página de manutenção

5. Preencha uma linha por defeito encontrado. Defeito inexistente listado aqui desconta pontos.

| # | Instrução | O que estava errado | O que você viu acontecer | Como corrigiu |
|---|---|---|---|---|
| 1 |`WORKDIR /usr/share/nginx`|O diretório estava errado, faltava entrar na pasta `/html` que é onde o nginx procura os arquivos|O site deu erro 404 (Not Found)|Alterei a linha para `WORKDIR /usr/share/nginx/html`|
| 2 |`COPY pagina/ .`|A pasta página não existe, e se existisse, os arquivos estariam sendo copiados para a pasta errada|O comando docker build quebrou com erro de arquivo não encontrado|Alterei a linha para `COPY site/. .`|
| 3 |Faltou instrução `EXPOSE 80`|Não tem instrução `EXPSOE 80` para documentar a porta|O Nginx usa a porta 80 por padrão|Adicionei o comando `EXPOSE 80`|

6. Qual a diferença entre `-p 7042:80` e `-p 80:7042` no `docker run`? Qual dos dois números é a porta do container?
- `-p 7042:80` Utiliza a porta 7042 da minha máquina e a porta 80 no container, `-p 80:7042` utiliza a porta 80 na minha máquina e a porta 7042 no container, o segundo número é a porta do container

## Parte 4 · Primeiro docker-compose

7. Escreva os dois comandos `docker run` que fariam o mesmo que o seu `docker-compose.yml`.

8. Qual comando derruba os dois containers de uma vez?

## Verificador

9. Código de conclusão impresso pelo verificador:

```
(cole aqui)
```
