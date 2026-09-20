# Atividade 1: Fundamentos e Características da Qualidade no LocalEats



## 1. Identificação

**Turma:** Qualidade de Software  
**Equipe:** Brian da Silva Guterres, 
            Maiara Torchelsen Saraiva, 
            Mateus Zanatta Mariani.

**Data:** 21/08/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Brian da Silva Guterres | [@brnsg] |
| Maiara Torchelsen Saraiva | [@maiatorchelsen] |
| Mateus Zanatta Mariani | [@mateus-zanatta] |

**Elemento de Competência:** Compreender os fundamentos de qualidade de software e sua aplicação no desenvolvimento de sistemas.

**Aplicação:** <https://local-eats-unisenac.vercel.app/>

---

## 2. Tarefa 1: Fundamentos da qualidade

### 2.1 Necessidades explícitas e implícitas

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
|---|---|---|---|
| Explícita | O sistema deve permitir criar conta e fazer login. | usuário | O usuário não consegue acessar sua conta e utilizar funcionalidades que dependem de autenticação. |
| Explícita | O sistema deve permitir que o usuário consiga selecionar o restaurante e pedir a comida | usuário | O usuário não consegue fazer o pedido de comida |
| Implícita | Todos os botões e abas clicáveis da interface (como "Cardápio" e "Avaliações") devem responder à interação do usuário e executar as ações esperadas (operabilidade). | usuário | O usuário clica em botões que não realizam ação alguma, gerando a percepção de que a página está travada ou quebrada. |
| Implícita | A barra de pesquisa deve filtrar os resultados exatamente pelos critérios indicados em seu texto orientador (como culinária e localização). | usuário | O usuário digita uma culinária no campo de busca e não encontra restaurantes, acreditando que a opção não existe na plataforma. |
| Implícita | O sistema deve exibir todas as mensagens de erro e validação de login no idioma padrão da aplicação (Português - Brasil). | usuário | O usuário não compreende a causa da falha no login ao se deparar com alertas em inglês ("Invalid credentials"), prejudicando a usabilidade. |
| Explícita | O usuário deve conseguir pesquisar restaurantes por especialidade ou localização. | Usuário | O usuário terá dificuldade para encontrar restaurantes de acordo com sua preferência ou região. |
| Implícita | A interface deve organizar seus elementos de forma clara, sem sobreposição ou agrupamento que dificulte a compreensão. | Usuário | O usuário pode não identificar os menus, botões e campos de busca, principalmente em telas menores. |
| Implícita | O sistema deve preservar as informações do carrinho e do pedido enquanto o usuário navega pela aplicação, evitando que itens adicionados desapareçam inesperadamente. | Usuário | O usuário pode perder os itens escolhidos, precisar refazer o pedido e abandonar a compra por frustração. |

### 2.2 Questão sobre os fundamentos da qualidade

**Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade? Justifiquem utilizando pelo menos uma necessidade implícita identificada pela equipe.**

Sim. Um sistema pode oferecer todas as funcionalidades solicitadas e ainda ter baixa qualidade se não atender necessidades implícitas dos usuários. No LocalEats, por exemplo, a interface deve permanecer organizada e utilizável em diferentes tamanhos de tela. Se botões, cabeçalho ou campos de busca ficarem sobrepostos ou difíceis de usar no celular, o usuário pode ter dificuldade para pesquisar restaurantes ou realizar pedidos.

---

## 3. Tarefa 2: Exploração da aplicação



| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
|---|---|---|---|---|
| Maiara Torchelsen | Tentativa de excluir um pedido do carrinho | uso esperado excluir o pedido | Não foi possível excluir pedido pois não tinha botão voltar ou retirar do carrinho | [ver evidência](evidencias/excluir%20um%20pedido.png) |
| Maiara Torchelsen | Em detalhes do produto ver o status de entrega  | Ao entrar nos pedidos visualizar o andamento do preparo até saída para entrega | Não foi possível visualizar os detalhes de entrega | [ver evidência](evidencias/detalhes-pedido.mp4) |
| Maiara Torchelsen| Validação de senha | Ao criar uma conta, informar uma senha com no mínimo 3 caracteres e impedir o cadastro/login de senhas menores que esse limite|O sistema informa que a senha deve ter no mínimo 3 caracteres, porém permite inserir e prosseguir com uma senha contendo menos de 3 caracteres | [ver evidência](evidencias/senha-menos-3.mp4) |
| Brian da Silva Guterres | Controle de abas (Tabs) de Cardápio e Avaliações na página do restaurante | **Uso esperado:** Clicar na aba "Avaliações" para exibir apenas as avaliações e ocultar o cardápio (e vice-versa ao clicar em "Cardápio"). <br>**Uso alternativo:** Clicar nos botões de aba e rolar a página para verificar a disposição dos conteúdos. | Os botões "Cardápio" e "Avaliações" são inoperantes e não alternam a exibição; ambos os conteúdos são renderizados juntos e de forma contínua um abaixo do outro na página, tornando os botões enganosos e sem funcionalidade real. | [ver evidência](evidencias/brian-abas-restaurante.mp4) |
| Brian da Silva Guterres | Barra de pesquisa de restaurantes e consistência com o placeholder | **Uso esperado:** Buscar restaurantes por nome ou termos gerais. <br>**Uso alternativo:** Digitar o nome de uma culinária (ex: "Italiana") na barra de pesquisa conforme instruído pelo texto do placeholder ("Buscar por culinária ou localização..."). | A busca não filtra por culinária no campo de texto (a filtragem de culinária só funciona nos botões de filtro abaixo), gerando uma contradição entre a instrução do placeholder e o comportamento real do sistema. | [ver evidência](evidencias/brian-busca-placeholder.mp4) |
| Brian da Silva Guterres | Autenticação e mensagens de validação no Login (Localização/Idioma) | **Uso esperado:** Realizar login com credenciais válidas. <br>**Uso alternativo:** Tentar efetuar login com credenciais incorretas (e-mail ou senha inválidos). | O sistema retorna a mensagem de erro em inglês ("Invalid credentials"), quebrando a consistência de idioma com o restante da aplicação que está em português brasileiro. | [ver evidência](evidencias/brian-login-idioma.png) |
| Mateus Zanatta Mariani | Visualização de restaurantes — mobile | Acessou a área inicial da aplicação em uma viewport mobile e observou a separação entre o cabeçalho e o bloco de imagem. | Foi observada falta de espaço entre os blocos da imagem e do cabeçalho. | [ver evidência](evidencias/falta%20espaço%20entre%20os%20blocos%20de%20imagem%20e%20cabeçalho.png) |
| Mateus Zanatta Mariani | Pesquisa de restaurantes — mobile | Acessou o campo de busca em uma viewport mobile e observou a posição do botão “Buscar”. | O botão “Buscar” apareceu sobre a caixa de busca, prejudicando a visualização e a interação com o campo. | [ver evidência](evidencias/botao%20buscar%20em%20cima%20da%20caixa%20de%20busca.png) |
| Mateus Zanatta Mariani | Explorar restaurantes — mobile | Rolou a página para baixo em uma viewport mobile. | Durante a rolagem, o cabeçalho ficou visualmente quebrado, conforme registrado na gravação. | [ver evidência](evidencias/Ao%20scrollar%20para%20baixo%20o%20cabeçalho%20fica%20quebrado.mp4) |


---

## 4. Tarefa 3: Requisitos e características de qualidade



| Integrante | Requisito de Qualidade | Característica ou subcaracterística | Justificativa | Como avaliar |
|---|---|---|---|---|
| Maiara Torchelsen | O sistema deve fornecer, na tela do carrinho, uma funcionalidade visível (botão ou ícone) para remover itens individuais ou esvaziar o carrinho antes da finalização do pedido. | Usabilidade / Operabilidade| A falta de um botão de exclusão impede que o usuário corrija erros ou mude de ideia, tornando a operação difícil e frustrante para o usuário. | Observar a interface do carrinho e confirmar a presença de botões "Remover" em cada item. |
| Maiara Torchelsen | O sistema deve disponibilizar uma tela de "Detalhes do Pedido" acessível após a compra, exibindo o status atualizado (ex: Recebido, Em Preparo, Saiu para Entrega, Entregue) e horário estimado. | Adequação Funcional / Integridade Funcional | O sistema falha em completar a tarefa de "consultar pedidos" se não fornece os detalhes essenciais e o andamento da entrega, que são objetivos críticos esperados pelo usuário em um sistema de delivery. | Verificar se, ao clicar em um pedido realizado, o sistema abre uma nova visualização, mostrando o status corresponde ao andamento do pedido no sistema. |
| Maiara Torchelsen | O sistema deve impedir o cadastro ou acesso quando a senha informada possuir menos de 3 caracteres, conforme a regra apresentada na tela. | Segurança / Confidencialidade | Permitir uma senha com menos de 3 caracteres, mesmo informando que o mínimo é 3, demonstra que a validação da regra de senha não está sendo aplicada corretamente e pode comprometer a segurança da conta do usuário. | Informar uma senha com menos de 3 caracteres e verificar se o sistema bloqueia o envio e apresenta uma mensagem informando que a senha deve possuir no mínimo 3 caracteres.|
| Brian da Silva Guterres | O sistema deve implementar a alternância efetiva entre as seções de Cardápio e Avaliações por meio do componente de abas, exibindo apenas o conteúdo correspondente à aba selecionada e mantendo um indicador visual claro do estado ativo. | Usabilidade / Operabilidade | A presença de controles inoperantes quebra o modelo mental do usuário (falsa affordance) e polui visualmente a tela ao exibir listas longas simultaneamente sem segregação. | Clicar na aba "Avaliações" e verificar se o cardápio fica oculto e apenas as avaliações permanecem visíveis, validando também o destaque visual na aba selecionada. |
| Brian da Silva Guterres | O mecanismo de busca textual deve indexar tanto nomes de restaurantes quanto categorias de culinária e localizações conforme sugerido pelo texto do campo, ou atualizar o placeholder para refletir apenas os critérios efetivamente suportados. | Adequação Funcional / Correção Funcional | Instruções textuais que não correspondem ao comportamento real do sistema induzem o usuário ao erro, fazendo-o supor incorretamente que o restaurante ou culinária não existem. | Digitar termos de culinária e localização na barra de busca e validar se a lista filtra os estabelecimentos que possuem essas características. |
| Brian da Silva Guterres | Todas as mensagens de erro, alertas e feedbacks no fluxo de login devem ser apresentados em português brasileiro (ex: "E-mail ou senha incorretos"), mantendo a consistência com o idioma da aplicação. | Usabilidade / Reconhecimento de Adequação | Exibir mensagens em idioma estrangeiro dificulta a compreensão por usuários não proficientes em inglês, comprometendo a clareza e a acessibilidade da interface. | Inserir credenciais inválidas no formulário de login e verificar se a mensagem de erro retornada está em português (pt-BR) e com terminologia clara. |
| Mateus Zanatta Mariani | Deve existir espaçamento visual suficiente entre o cabeçalho e o bloco de imagem para que os componentes possam ser distinguidos claramente em dispositivos mobile. | Usabilidade — estética da interface do usuário | A falta de espaço entre os blocos dificulta a separação visual das áreas da página e torna a interface menos clara. | Verificar, em diferentes larguras mobile, se há separação visível entre o cabeçalho e a imagem, sem encostamento ou sobreposição. |
| Mateus Zanatta Mariani | Em uma viewport mobile, o botão “Buscar” deve permanecer completamente visível e separado do campo de pesquisa, permitindo que ambos sejam utilizados sem sobreposição. | Usabilidade — operabilidade | A busca é uma ação importante para encontrar restaurantes. Se o botão cobre o campo, o usuário pode ter dificuldade para digitar ou acionar a pesquisa. | Testar a busca em diferentes larguras mobile e verificar se o texto do campo, o botão e a área de toque permanecem visíveis e independentes. |
| Mateus Zanatta Mariani | Ao rolar a página em uma viewport mobile, o cabeçalho deve manter sua estrutura visual e não apresentar quebra de layout. | Usabilidade — estética da interface do usuário | A quebra visual do cabeçalho prejudica a percepção de organização e pode dificultar a navegação durante a exploração dos restaurantes. | Gravar a rolagem da página em diferentes viewports mobile e comparar a aparência do cabeçalho antes, durante e depois da rolagem. |


---

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
Perplexity | Nemotron 3 ultra | Chatgpt

**Como foi utilizada:**  
A ferramenta foi utilizada para auxiliar na interpretação do enunciado, organizar os registros das evidências, formular requisitos de qualidade e relacioná-los às características de qualidade aplicáveis ao LocalEats.

**Como as respostas foram verificadas:**  
As sugestões foram comparadas com o enunciado da atividade e com as capturas de tela e gravação produzidas pela equipe. Os integrantes devem revisar os nomes, confirmar a correspondência dos arquivos e explicar as observações e decisões durante a defesa técnica.
