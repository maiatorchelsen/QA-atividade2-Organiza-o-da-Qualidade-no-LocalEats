# Atividade 3: Estratégia e Projeto de Testes do LocalEats


## 1. Identificação

**Turma:** Qualidade de Software (ADS5N26-2C) - 78 
**Equipe:**  Maiara
**Data:** 18/09/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Maiara Torchelsen Saraiva | @maiatorchelsen |


**Elemento de Competência:** Planejar e projetar testes selecionando técnicas adequadas.

**Aplicação:** <https://local-eats-unisenac.vercel.app/>

---

## 2. Tarefa 1: Planejamento dos testes

### 2.1 Objetivo dos testes

Garantir que os usuários consigam selecionar itens, calcular corretamente o valor total do carrinho e concluir pedidos de forma íntegra, impedindo a submissão de pedidos vazios ou com ausência de dados obrigatórios.

### 2.2 Escopo

#### Funcionalidades incluídas

| Integrante | Funcionalidade incluída | O que será verificado |
|---|---|---|
| Maiara Torchelsen Saraiva | Fazer pedido | Adição de itens ao carrinho, cálculo do valor total dos produtos e validação do fluxo de confirmação do pedido.  |



#### Funcionalidade não incluída

| Funcionalidade não incluída | Justificativa |
|---|---|
| Consultar pedidos | Não faz parte do fluxo prioritário de criação e finalização da compra nesta etapa de testes. |

### 2.3 Abordagem

| Item | Decisão da equipe | Justificativa |
|---|---|---|
| Níveis de teste | Sistema | O fluxo será analisado pela interface gráfica, do início ao fim (ponta a ponta). |
| Tipos de teste | Funcional | O objetivo é verificar o cumprimento das regras de negócio do carrinho de compras e checkout.|
| Perspectiva caixa-preta ou caixa-branca | Caixa-preta |  Serão consideradas entradas e resultados observáveis pela interface do usuário, sem acesso ao código-fonte.  |
| Técnicas de teste | Análise de Valor Limite e Tabela de Decisão | Para testar as fronteiras da quantidade de itens no carrinho e as combinações de condições necessárias para a finalização do pedido.  |

### 2.4 Ambiente e responsabilidades

| Item | Definição |
|---|---|
| Ambiente necessário | Aplicação hospedada em `https://local-eats-unisenac.vercel.app/`, navegadores Chrome ou Firefox atualizados, conexão estável com a internet e conta de usuário previamente cadastrada.  |
| Responsáveis pelo planejamento | Maiara Torchelsen Saraiva |
| Responsáveis pela especificação dos casos | Maiara Torchelsen Saraiva |
| Responsáveis pela futura execução |Maiara Torchelsen Saraiva |

### 2.5 Critérios

| Critério | Definição da equipe |
|---|---|
| Entrada | Aplicação disponível na Vercel, usuário devidamente cadastrado/autenticado e cardápio de restaurante com itens acessíveis. |
| Saída | Todos os três casos de teste planejados executados e seus respectivos resultados registrados. |
| Suspensão |  Indisponibilidade total do ambiente da aplicação na Vercel ou falha crítica que impeça a autenticação do usuário. |

---

## 3. Tarefa 2: Riscos e técnicas de teste

### 3.1 Análise dos riscos

> Cada integrante deve analisar pelo menos um risco relacionado à funcionalidade escolhida. No trabalho individual, devem ser analisados dois riscos.

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
|---|---|---|---|---|:---:|:---:|:---:|---|
| R01 | Maiara Torchelsen Saraiva | Fazer pedido  | Permitir a finalização do pedido com carrinho vazio | O restaurante recebe uma requisição inválida e o sistema processa um pedido sem itens, gerando inconsistência operacional  |Alto | Alto| Alto |  Compromete diretamente o fluxo principal de vendas e a confiabilidade da aplicação.|
| R02 | Maiara Torchelsen Saraiva |  Fazer pedido | Sumarização ou cálculo incorreto do valor dos itens do carrinho | O cliente é cobrado por um valor diferente do preço anunciado dos produtos, gerando insatisfação e cancelamentos | Alto | Alto | Alto | Inconsistências em cálculos financeiros afetam diretamente a confiança do usuário no sistema. |


### 3.2 Aplicação das técnicas

> Cada integrante deve aplicar pelo menos uma técnica adequada à funcionalidade e ao risco analisado. A equipe deve utilizar, no conjunto da atividade, pelo menos duas técnicas diferentes.

#### Análise do integrante 1

**Integrante:** Maiara Torchelsen Saraiva
**Funcionalidade:** Fazer pedido 
**Risco relacionado:** R01 e R02 
**Técnica escolhida:** Análise de Valor Limite e Tabela de Decisão  

**Por que a técnica foi escolhida:**  
A Análise de Valor Limite foi escolhida para testar as fronteiras da quantidade de itens permitidos no carrinho (mínimo de 1 item). A Tabela de Decisão foi escolhida para mapear as combinações de condições necessárias (presença de itens no carrinho e endereço preenchido) para liberar a ação de finalização do pedido.


**Aplicação da técnica:**  
**Técnica 1: Análise de Valor Limite (Quantidade de itens no carrinho)**
* Limite inferior válido: 1 item.
* Classe Inválida: 0 itens (abaixo do limite mínimo).
* Classe Válida: 1 item (limite exato) e 2 itens (acima do limite mínimo).

**Técnica 2: Tabela de Decisão (Liberação de checkout)**

| Regra | Possui itens no carrinho? | Endereço de entrega informado? | Resultado esperado |
|:---:|:---:|:---:|---|
| **1** | Não | Não | Impedir a finalização / Botão desabilitado |
| **2** | Sim | Não | Bloquear confirmação e solicitar preenchimento do endereço |
| **3** | Sim | Sim | Permitir confirmação do pedido com sucesso |


**Casos derivados:** CT01, CT02 e CT03



---

## 4. Tarefa 3: Casos de teste e rastreabilidade

### 4.1 Casos de teste


### CT01: Bloquear tentativa de finalizar pedido com carrinho vazio


**Integrante responsável:** Maiara Torchelsen Saraiva  
**Funcionalidade:** Fazer pedido
**Risco ou requisito relacionado:** R01  
**Técnica utilizada:**  Análise de Valor Limite

**Pré-condição:**  
O usuário está autenticado no sistema e acessou a tela do carrinho de compras sem nenhum produto selecionado.

**Dados de entrada:**  
Quantidade de itens no carrinho: `0`.


**Passos:**

1. Navegar até a página ou modal do Carrinho de Compras.
2. Verificar o estado do botão "Finalizar Pedido" ou tentar clicar sobre ele.


**Resultado esperado:**  
O botão de finalização permanece desabilitado ou o sistema exibe a mensagem "Seu carrinho está vazio", impedindo a criação do pedido.


---

### CT02: Validar cálculo e confirmação do pedido com a quantidade mínima (1 item)

**Integrante responsável:** Maiara Torchelsen Saraiva  
**Funcionalidade:**  Fazer pedido 
**Risco ou requisito relacionado:** R01 e R02 
**Técnica utilizada:** Análise de Valor Limite

**Pré-condição:**  
O usuário está autenticado no sistema e com a página de um restaurante selecionado aberta.

**Dados de entrada:**  
Item: "Prato Executivo" (Quantidade: `1`, Valor unitário: `R$ 25,00`).


**Passos:**

1. Adicionar 1 unidade do "Prato Executivo" ao carrinho.
2. Acessar o Carrinho de Compras.
3. Confirmar o valor total exibido na tela.
4. Clicar no botão "Finalizar Pedido".


**Resultado esperado:**  
O valor total é exibido corretamente como `R$ 25,00`, o pedido é processado com sucesso e o sistema exibe a mensagem de confirmação do pedido.

### CT03: Impedir finalização do pedido sem informar o endereço de entrega

**Integrante responsável:** Maiara Torchelsen Saraiva  
**Funcionalidade:** Fazer pedido  
**Risco ou requisito relacionado:** R02  
**Técnica utilizada:** Tabela de Decisão  

**Pré-condição:**  
O usuário está autenticado no sistema e possui 1 item adicionado ao carrinho de compras.

**Dados de entrada:**  
Itens no carrinho: `1`, Campo Endereço: `Vazio / Não informado`.

**Passos:**

1. Acessar a tela de checkout ou carrinho com o produto selecionado.
2. Garantir que a seleção ou campo de endereço esteja em branco.
3. Clicar no botão "Finalizar Pedido".

**Resultado esperado:**  
O sistema exibe um alerta informando a necessidade de preencher o endereço de entrega e não conclui a criação do pedido.


---


### 4.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
|---|---|---|---|---|
| Maiara Torchelsen Saraiva  | Fazer pedido  | R01 | Análise de Valor Limite | CT01 e CT02 |
| Maiara Torchelsen Saraiva |  Fazer pedido | R02 | Análise de Valor Limite e Tabela de Decisão | CT02 e CT03 |


---

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
Gemini.

**Como foi utilizada:**  
Auxílio na estruturação da documentação em Markdown conforme o modelo da disciplina, priorização de riscos do fluxo de e-commerce e aplicação formal das técnicas de Análise de Valor Limite e Tabela de Decisão.


**Uma sugestão que precisou ser alterada ou rejeitada:**  
[Descrever brevemente. Caso nenhuma sugestão tenha sido rejeitada, expliquem como as sugestões foram analisadas criticamente.]

**Como as respostas foram verificadas:**  
A ferramenta sugeriu originalmente incluir a validação da taxa de entrega/frete no cálculo do valor total. A sugestão foi alterada após análise do site real do LocalEats (`https://local-eats-unisenac.vercel.app/`), constatando que a aplicação atual calcula diretamente o somatório dos produtos selecionados, sem etapa de frete.
