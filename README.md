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

- **Java 17+**
- **Spring Boot** (Web, Data JPA)
- **Banco de Dados**: H2 (padrão, fácil substituição por MySQL, PostgreSQL, etc)
- **Maven** para gerenciamento de dependências
- **Lombok** para redução de boilerplate

## Como Executar

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/taisdias76/Inventario.git
   cd Inventario
   ```

2. **Configure o banco de dados** (opcional):  
   Por padrão, o projeto utiliza o banco de dados H2 em memória. Para usar outro banco, edite o arquivo `application.properties`.

3. **Compile o projeto:**
   ```bash
   mvn clean install
   ```

4. **Execute a aplicação:**
   ```bash
   mvn spring-boot:run
   ```

5. **Acesse a aplicação:**
   - API: `http://localhost:8080`
   - (Opcional) Swagger: `http://localhost:8080/swagger-ui.html`

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

## Exemplos de Uso

### Cadastro de Item

```json
POST /api/product
{
   "name": "Jogo de Pastilhas de Freio Dianteiro",
   "description": "Jogo de pastilhas de freio dianteiro (cerâmica)",
   "price": 150.00,
   "quantity": 10,
   "category": "Frenagem",
}
```

### Cadastro de Categoria

```json
POST /api/category
{
  "category": "Frenagem"
}
```

### Cadastro de Fornecedor

```json
POST /api/supplier
{
  "name": "Fras-le"
}
```

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

## Licença

Este projeto está licenciado sob a licença MIT.

---

> Feito com Java e Spring Boot para facilitar o controle de inventários.
