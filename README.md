# curso-alura-spring-testes-deploy

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
