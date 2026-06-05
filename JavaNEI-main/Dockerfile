# =====================================================
# Stage 1 - BUILD
# =====================================================
FROM maven:3.9.6-eclipse-temurin-21 AS build

WORKDIR /build

COPY pom.xml .
RUN mvn dependency:go-offline -B

COPY src ./src
RUN mvn clean package -DskipTests -B

# =====================================================
# Stage 2 - RUNTIME
# =====================================================
FROM eclipse-temurin:21-jre-alpine

# Variáveis de ambiente da aplicação
ENV APP_PORT=8080 \
    SPRING_PROFILES_ACTIVE=prod \
    DB_URL=jdbc:oracle:thin:@oracle.fiap.com.br:1521:ORCL \
    DB_USERNAME=rm564232 \
    DB_PASSWORD=260407 \
    NASA_API_KEY=s9gF1rPUkfxgXPIEvKZ4sc5SiLbaM5hKTQGmkCSM \
    JWT_SECRET=senhaSecreta123 \
    JWT_EXPIRATION=30

# Criar usuário não privilegiado
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# Diretório de trabalho da aplicação
WORKDIR /app/nei-asteroid-monitor

# Copiar o JAR gerado no stage de build
COPY --from=build /build/target/*.jar app.jar

# Ajustar permissões para o usuário não privilegiado
RUN chown -R appuser:appgroup /app/nei-asteroid-monitor

# Trocar para o usuário não privilegiado
USER appuser

# Expor a porta da aplicação
EXPOSE 8080

# Comando de inicialização
ENTRYPOINT ["java", \
  "-Dspring.datasource.url=${DB_URL}", \
  "-Dspring.datasource.username=${DB_USERNAME}", \
  "-Dspring.datasource.password=${DB_PASSWORD}", \
  "-Dnasa.api.key=${NASA_API_KEY}", \
  "-Djwt.secret=${JWT_SECRET}", \
  "-Djwt.expiration=${JWT_EXPIRATION}", \
  "-jar", "app.jar"]