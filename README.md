# Inventario

Sistema para oficina mecânica e autopeças. Problema: controle de peças, consumo por ordem de serviço e fila de compras. Fase atual: base funcional em evolução, com cadastro e consulta de produtos, categorias e fornecedores.

## Status das funcionalidades

| Funcionalidade | Status |
| --- | --- |
| Cadastro de categoria | implementado |
| Listagem de categorias | implementado |
| Cadastro de produto | implementado |
| Listagem de produtos | implementado |
| Cadastro de fornecedor | implementado |
| Listagem de fornecedores | implementado |
| Controle de consumo por ordem de serviço | planejado |
| Fila de compras | planejado |
| Integração com ERP/CRM | fora de escopo |

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
POST /api/itens
{
  "nome": "Jogo de Pastilhas de Freio Dianteiro",
  "categoria": "Frenagem",
  "quantidade": 10,
  "descricao": "Jogo de pastilhas de freio dianteiro (cerâmica)"
}
```

### Movimentação de Estoque

```json
POST /api/movimentacoes
{
  "itemId": 1,
  "tipo": "SAIDA",
  "quantidade": 1,
  "observacao": "Peça aplicada no veículo Placa ABC-1234 conforme O.S. 5678"
}
```

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

## Licença

Este projeto está licenciado sob a licença MIT.

---

> Feito com Java e Spring Boot para facilitar o controle de inventários.
