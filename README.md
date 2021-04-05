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

## Aulas
### Módulo 04 - Delpoy
#### Aula 04.02 - Gerando o jar da aplicação
- Para gerar o jar da aplicação usando eclipse clique com o `botão direito do mouse no projeto > Run as > Maven install`
- Para gerar o jar via linha de comando no terminal execute `./mvnw clean package`.
- O jar é gerado dento da pasta target, na raiz do projeto
- Para executar a aplicação execute `java -jar nomeDoArquivo.jar`, dentro do diretório `target`.

## Anotações
- comando para execução de teste de repositório na linha de comando:
```bash
./mvnw clean test -Dtest=br.com.alura.forum.repository.CursoRepositoryTest -e
```

- comando para execução de teste de controller na linha de comando:
```bash
./mvnw  test -Dtest=br.com.alura.forum.controller.AutenticacaoControllerTest -e
```

- exemplo de inicialização da aplicação via linha de comando:
```bash
java -jar -Dspring.profiles.active=prod forum.jar
```

- exemplo de adição de variáveis de ambiente:
```bash
export FORUM_DATABASE_URL=jdbc:h2:mem:alura-forum
export FORUM_DATABASE_USERNAME=sa
export FORUM_DATABASE_PASSWORD=
export FORUM_JWT_SECRET=123456
```

- exemplo de inicialização da aplicação passando as variáveis de ambiente
```bash
java -jar -Dspring.profiles.active=prod -DFORUM_DATABASE_URL=jdbc:h2:mem:alura-forum -DFORUM_DATABASE_USERNAME=sa -DFORUM_DATABASE_PASSWORD= -DFORUM_JWT_SECRET=123456 forum.jar
```
- [Exemplo de configuração para deploy tradicional com arquivo war](https://github.com/my-study-area/curso-alura-spring-testes-deploy/commit/33c9572fc257f50434d5f8fbaa4e97927c3ff529)

- comando para criar imagem docker da aplicação:
```bash
docker build -t alura/forum .
```

- comando para inicializar container com variáveis de ambiente:
```bash
docker run -p 8080:8080 -e SPRING_PROFILES_ACTIVE='prod' -e FORUM_DATABASE_URL='jdbc:h2:mem:alura-forum' -e FORUM_DATABASE_USERNAME='sa' -e FORUM_DATABASE_PASSWORD='' -e FORUM_JWT_SECRET='123456' -e PORT='8080' alura/forum
```

- [Comandos para onfiguração e deploy do docker no Heroku](https://devcenter.heroku.com/articles/container-registry-and-runtime)
