# curso-alura-spring-testes-deploy

<p>
    <img alt="GitHub top language" src="https://img.shields.io/github/languages/top/my-study-area/curso-alura-spring-testes-deploy">
    <a href="https://github.com/my-study-area">
        <img alt="Made by" src="https://img.shields.io/badge/made%20by-adriano%20avelino-gree">
    </a>
    <img alt="Repository size" src="https://img.shields.io/github/repo-size/my-study-area/curso-alura-spring-testes-deploy">
    <a href="https://github.com/EliasGcf/readme-template/commits/master">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/my-study-area/curso-alura-spring-testes-deploy">
    </a>
</p>

```bash
./mvnw clean test -Dtest=br.com.alura.forum.repository.CursoRepositoryTest -e
```

```bash
./mvnw  test -Dtest=br.com.alura.forum.controller.AutenticacaoControllerTest -e
```

```bash
java -jar -Dspring.profiles.active=prod forum.jar
```

```bash
export FORUM_DATABASE_URL=jdbc:h2:mem:alura-forum
export FORUM_DATABASE_USERNAME=sa
export FORUM_DATABASE_PASSWORD=
export FORUM_JWT_SECRET=123456
```

```bash
java -jar -Dspring.profiles.active=prod -DFORUM_DATABASE_URL=jdbc:h2:mem:alura-forum -DFORUM_DATABASE_USERNAME=sa -DFORUM_DATABASE_PASSWORD= -DFORUM_JWT_SECRET=123456 forum.jar
```
[Exemplo de configuração para deploy tradicional com arquivo war](https://github.com/my-study-area/curso-alura-spring-testes-deploy/commit/33c9572fc257f50434d5f8fbaa4e97927c3ff529)

cria imagem docker da aplicação:
```bash
docker build -t alura/forum .
```

inicia container com variáveis de ambiente:
```bash
docker run -p 8080:8080 -e SPRING_PROFILES_ACTIVE='prod' -e FORUM_DATABASE_URL='jdbc:h2:mem:alura-forum' -e FORUM_DATABASE_USERNAME='sa' -e FORUM_DATABASE_PASSWORD='' -e FORUM_JWT_SECRET='123456' alura/forum
```

[Comandos para onfiguração e deploy do docker no Heroku](https://devcenter.heroku.com/articles/container-registry-and-runtime)
