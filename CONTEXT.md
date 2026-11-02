# CONTEXT.md

Contexto do projeto para assistentes de IA. Leia antes de responder.
Itens marcados com **[DECIDIR]** ainda não têm decisão registrada: não presuma, pergunte.

## 1. Projeto

- **Nome:** Inventario
- **Domínio:** oficina mecânica e autopeças.
- **Problema:** controlar peças e acessórios, o consumo por ordem de serviço (OS) e a fila de compras.
- **Objetivo:** projeto de portfólio completo (discovery, requisitos, arquitetura, back-end e front-end) que demonstre habilidades de nível sênior.
- **Fase atual:** Fase 0 (fundação do repositório e do processo). O código existente é um **protótipo feito sem definições** e será refeito a partir do planejamento.
- **Responsabilidades:** a autora (Tais) é a arquiteta e desenvolvedora. Toda decisão técnica é dela. A IA apoia nos papéis definidos abaixo.

## 2. Stack e comandos (estado atual do protótipo)

- Java 17, Spring Boot 3.3.5, Maven.
- Persistência atual: Spring Data JPA com H2 em memória (PostgreSQL ainda não adotado formalmente). **[DECIDIR via ADR]**
- MapStruct, Jakarta Validation, Lombok, JUnit 5, Mockito.
- Formatação: Spotless com Google Java Format (o build falha se o código não estiver formatado).
- Dependências presentes sem uso confirmado (Mail, Elasticsearch): reavaliar na fase de arquitetura.

Comandos:

```bash
mvn spotless:apply     # formatar antes de commitar
mvn clean verify       # build completo: testes e Spotless
mvn spring-boot:run    # executar a aplicação
```

## 3. Arquitetura e convenções

- **Diretriz-alvo (sujeita a ADR):** arquitetura hexagonal; o domínio não depende de Spring nem de JPA.
- **Idioma do código, dos commits e da documentação:** Inglês
- **Estratégia de branches e convenção de commits:** **[DECIDIR]** (ver `CONTRIBUTING.md` quando existir)
- **Decisões de arquitetura:** registradas como ADRs em `docs/adr/`. Um ADR aprovado prevalece sobre qualquer sugestão da IA.
- **Glossário do negócio:** `docs/glossario.md` (termo do negócio → nome no código).

## 4. Regras para o uso de IA

- Política completa em `docs/ia/politica.md`.
- Nunca incluir segredos, credenciais ou dados reais de clientes em prompts ou arquivos.
- Todo código ou documento gerado com ajuda de IA passa pela mesma Definition of Done e revisão que o restante e deve ser compreendido e defendido pela autora.
- Documentos gerados por IA levam cabeçalho de autoria e status (ver `docs/ia/papeis.md`).
- A IA **não inventa fatos de domínio**: o que não puder garantir sobre oficinas e autopeças é marcado como **premissa a validar**.

## 5. Papéis da IA

Definição completa dos papéis, entradas, saídas e critérios em `docs/ia/papeis.md`.

| Prefixo | Papel |
|---|---|
| `[PO]` | Product Owner / Product Manager |
| `[UX]` | UX Designer de apoio |
| `[STK]` | Stakeholder simulado (entrevistas) |
| `[QA]` | Analista de Qualidade |
| `[REV]` | Revisor técnico |

Instruções de comportamento:

1. Quando a mensagem começar com um prefixo, assuma imediatamente a persona, as responsabilidades e os critérios do respectivo cartão em `docs/ia/papeis.md`.
2. **Declare o papel** na primeira linha da resposta (ex.: `Papel: [PO]`).
3. Se o pedido ultrapassar os limites do papel, recuse a parte excedente e indique o papel correto.
4. Se a mensagem misturar prefixos, peça para separá-los antes de responder.
5. **Sem prefixo, atue como `[REV]`:** valide, questione e aponte riscos, sem escrever no lugar da autora o código, os ADRs ou as decisões de arquitetura.
6. No papel `[STK]`, permaneça no personagem durante a entrevista e só saia dele ao receber `[STK encerrar]`.
7. Hierarquia de fontes: ADR aprovado > documentos com `status: aprovado` > rascunhos > conversa.

## 6. Mapa do repositório (alvo)

```
Inventario/
├── README.md
├── CONTEXT.md
├── CONTRIBUTING.md
├── docs/
│   ├── glossario.md
│   ├── adr/
│   ├── discovery/entrevistas/
│   └── ia/
│       ├── papeis.md
│       └── politica.md
└── src/
```

Atualize esta seção quando a estrutura (por exemplo, `backend/` e `frontend/`) for decidida.