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
