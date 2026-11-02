# Política de Uso de Assistentes de Inteligência Artificial

Esta política define as diretrizes para o uso de ferramentas de IA no desenvolvimento de software da nossa equipe. O objetivo é garantir a segurança da informação, a qualidade do código e a responsabilidade técnica.

## 1. Segurança e Privacidade de Dados
* **Nunca envie segredos:** É terminantemente proibido colar chaves de API, senhas, tokens de acesso ou credenciais em qualquer assistente de IA.
* **Dados Sensíveis:** Não envie dados reais de clientes, informações financeiras ou propriedade intelectual crítica não pública.
* **Anonimização:** Sempre mascare ou use dados fictícios ao pedir ajuda com trechos de código ou modelagem de dados.

## 2. Qualidade e Processo (DoD & Review)
* **Mesmo Padrão de Exigência:** Todo código gerado ou sugerido por IA deve passar exatamente pela mesma **Definition of Done (DoD)** estabelecida para o projeto.
* **Code Review:** O código gerado por IA não tem passe livre. Ele deve ser revisado por pares via Pull Request com o mesmo rigor (ou maior) aplicado ao código escrito por humanos.
* **Testes:** Garanta que testes unitários e de integração cubram o comportamento do código gerado.

## 3. Responsabilidade Técnica (Propriedade do Código)
* **Entendimento Total:** Você é o autor final do código. Você deve **entender e ser capaz de defender cada linha** de código gerada por IA que for integrada ao repositório.
* **Sem "Caixa Preta":** Se você não compreende o que o assistente gerou, o código não deve ser commitado. Refatore ou peça explicações até dominar a lógica implementada.
