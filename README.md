# Inventario

Sistema para oficina mecânica e autopeças. Problema: controle de peças, consumo por ordem de serviço e fila de compras. Fase atual: Fase 0 (fundação); código existente é um protótipo e o escopo será definido na Fase 1 (discovery).

## Status das funcionalidades

| Funcionalidade | Status |
|---|---|
| Categorias: cadastro e listagem | protótipo |
| Produtos: cadastro e listagem | protótipo |
| Fornecedores: cadastro e listagem | protótipo |
| Controle de consumo por ordem de serviço | planejado |
| Fila de compras | planejado |

**protótipo:** existe no código atual, não é compromisso de produto e será revisto na Fase 1. **planejado:** faz parte da visão do projeto e ainda não existe.

## Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3.3.5** (Spring Web e Spring Data JPA)
- **Banco em memória padrão**: H2; o projeto também declara o driver JDBC do PostgreSQL
- **Lombok** para redução de boilerplate
- **Maven Wrapper** para compilar e executar sem instalar Maven separadamente

## Como Executar

### Pré-requisitos

- JDK 17 instalado (`java -version` deve indicar a versão 17).
- Git para clonar o repositório.
- Não é necessário instalar Maven: use o Maven Wrapper incluído no projeto.

### Passos

1. **Clone o repositório:**
   ```console
   git clone https://github.com/taisdias-dev/Inventario.git
   cd Inventario
   ```

2. **Compile e execute os testes:**

   Linux/macOS:
   ```console
   ./mvnw clean verify
   ```

   Windows (Prompt de Comando):
   ```console
   mvnw.cmd clean verify
   ```

   Windows (PowerShell):
   ```powershell
   .\mvnw.cmd clean verify
   ```

3. **Inicie a aplicação:**

   Linux/macOS:
   ```console
   ./mvnw spring-boot:run
   ```

   Windows (Prompt de Comando):
   ```console
   mvnw.cmd spring-boot:run
   ```

   Windows (PowerShell):
   ```powershell
   .\mvnw.cmd spring-boot:run
   ```

4. **Verifique a listagem de produtos** (protótipo). Com a aplicação em execução:
   ```console
   curl -i http://localhost:8080/api/products
   ```

   Resposta esperada em uma instalação nova:
   ```http
   HTTP/1.1 200
   Content-Type: application/json

   []
   ```

## Estrutura do Projeto

```
Inventario/
 ├── src/
 │   ├── main/
 │   │   ├── java/
 │   │   │   └── ... (código fonte)
 │   │   └── resources/
 │   │       └── application.properties
 │   └── test/
 │       └── ... (testes)
 ├── pom.xml
 └── README.md
```

---

> Feito com Java e Spring Boot para facilitar o controle de inventários.
