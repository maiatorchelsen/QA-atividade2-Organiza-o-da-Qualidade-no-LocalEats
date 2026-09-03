Atividade 2: Organização da Qualidade no LocalEats
Substituam os campos entre colchetes pelas respostas da equipe e removam as instruções antes da entrega.

1. Identificação

Turma: Qualidade de Software (ADS5N26-2C) - 78 

Equipe: 

Data: 02/09/2026

Integrantes
Nome	Maiara Torchelsen Saraiva

Usuário no GitHub @maiatorchelsen



**Elemento de Competência:** Identificar papéis, responsabilidades e competências relacionadas às atividades de qualidade e testes.

---

## 2. Tarefa 1: Diagnóstico da situação

### 2.1 Problemas organizacionais
| Problema identificado | Possível consequência para o produto ou para a equipe |
|---|---|
| *Falta de clareza nos critérios de pronto (Definition of Done)* | Entrega de funcionalidades incompletas ou com bugs para os usuários finais, gerando insatisfação e retrabalho constante para a equipe. |
| *Crença de que a qualidade é responsabilidade exclusiva do QA* | Sobrecarga do analista de QA, gargalos no fluxo de entregas, falta de testes unitários pelos desenvolvedores e baixa cultura de prevenção de defeitos. |
| *Ausência de processo padronizado para registro e acompanhamento de defeitos* | Falhas conhecidas caindo no esquecimento, perda de rastreabilidade de bugs críticos e falta de previsibilidade sobre a real estabilidade do sistema. |
| *Indefinição de papéis e responsabilidades (Relato: Não está claro quem aprova a versão e algumas atividades têm múltiplos responsáveis ou nenhum)* | Clima de "jogo de empurra" durante incidentes críticos, retrabalho e ruídos de comunicação por falta de um fluxo de decisão estruturado.|



### 2.2 Responsabilidade pela qualidade
**A qualidade do LocalEats deve ser responsabilidade exclusiva do profissional de QA? Justifiquem.**

Não, a qualidade do LocalEats não deve ser responsabilidade exclusiva do QA. A qualidade é um compromisso compartilhado por todo o time ágil. Enquanto os desenvolvedores garantem a qualidade do código e testes unitários, o Product Owner alinha os requisitos e o QA atua como um facilitador das melhores práticas de testes, prevenindo falhas em vez de apenas procurá-las ao final do fluxo.


## 3. Tarefa 2: Papéis e competências



| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
|---|---|---|---|---|
| Maiara | Responsável pelo Produto (Product Owner) | Definir critérios de aceitação; priorizar a correção de defeitos; esclarecer dúvidas de negócio. | Gestão de backlog, técnicas de detalhamento de requisitos (User Stories, BDD), métricas de produto. | Comunicação clara, negociação, visão estratégica, tomada de decisão. |
| Maiara | Desenvolvedor(a) | Escrever código limpo; criar e executar testes unitários; revisar código de pares; corrigir bugs identificados. | Linguagens de programação, arquitetura de software, frameworks de testes unitários/integrados, Git. | Trabalho em equipe, atenção aos detalhes, receptividade a feedbacks, resiliência. |
| Maiara | Analista de Qualidade (QA) | Planejar e executar testes de sistema; apoiar a escrita de critérios de aceitação; registrar e acompanhar defeitos. | Estratégias de testes (manuais e automatizados), BDD/Gherkin, ferramentas de gestão de defeitos e testes de API. | Pensamento crítico, empatia com o usuário, boa comunicação, perfil analítico. |
| Maiara | DevOps / Liderança Técnica | Garantir pipeline de CI/CD para automação de testes; aprovar/apoiar a disponibilização de versão; manter ambiente de testes. | Integração e entrega contínuas (CI/CD), infraestrutura como código, monitoramento de ambientes, Git.| Liderança facilitadora, visão integrada do processo, proatividade, solução de problemas. |


    

## 4. Tarefa 3: Matriz de responsabilidades



Utilizem:

- **R:** responsável por executar a atividade;
- **A:** aprovador ou responsável final;
- **C:** consultado antes da execução ou decisão;
- **I:** informado sobre o resultado.

| Atividade de qualidade | PO (Product Owner) | Desenvolvedor | QA | DevOps / Tech Lead |
|---|:---:|:---:|:---:|:---:|
| Definir critérios de aceitação |A/R  | C| C |  I|
| Revisar requisitos | A | R |R  | C |
| Implementar a funcionalidade | I | A/R | C | I |
| Revisar o código | I | A/R | I |C  |
| Criar testes unitários |I  | A/R | C | I |
| Planejar e executar testes do sistema | I | C | A/R | I |
| Registrar e acompanhar defeitos | I | C | A/R | I |
| Priorizar a correção dos defeitos |A  | R | R | I |
| Aprovar a disponibilização da versão | A | C | C | R |


### 4.1 Lacuna ou conflito encontrado

**Lacuna ou conflito:**  
Aprovação e Disponibilização da Versão: Anteriormente no LocalEats, não havia clareza sobre quem autorizava a ida para produção. Na matriz configurada, definiu-se que o PO é o Aprovador (A) final sob a perspectiva de negócio, enquanto o DevOps/Tech Lead é o Responsável (R) pela execução segura da implantação técnica. A falta desta divisão causava incerteza e liberações com bugs não auditados.

**Consequência:**  
A falta de um alinhamento claro sobre quem valida o negócio e quem cuida da parte técnica na hora do deploy gera ruídos na rotina da equipe e afeta diretamente a ponta final do LocalEats:

Para o produto: Entregas feitas "no escuro" aumentam a chance de o app cair ou apresentar falhas críticas logo após uma atualização — como o cliente não conseguir fechar o pedido ou o restaurante não receber a notificação. Isso desgasta a confiança que os parceiros e usuários têm na plataforma.

Para a equipe: Quando algo dá errado em produção, cria-se aquele clima desconfortável de procurar culpados ("quem liberou isso?"). Além disso, o time técnico acaba vivendo em um ciclo cansativo de apagar incêndios e fazer hotfixes na correria, em vez de focar na evolução contínua e planejada da aplicação.



### 4.2 Práticas de QA recomendadas

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
|---|---|---|
| Sessões de "Three Amigos" (Alinhamento Prévio de Requisitos) | Requisitos ambíguos, falta de critérios de aceitação claros e bugs identificados tardiamente em produção. | Product Owner, Desenvolvedor e QA.|
| Definição de Definition of Done (DoD) com testes obrigatórios | Funcionalidades consideradas prontas com defeitos e falta de testes unitários ou de integração antes da entrega. | Time de Desenvolvimento, QA, PO e DevOps/Tech Lead. |
| Automação de Testes de Regressão e Integração Contínua (CI/CD) | Gargalos nas validações manuais antes de cada release, regressões não detectadas e lentidão na implantação do produto. | QA, Desenvolvedor e DevOps / Tech Lead. |
| Triagem Periódica de Defeitos de Pedido e Entrega | Correções de bugs sem critério de negócio, atrasos no ciclo de correção de falhas críticas (ex: falhas no checkout/pagamento) e acúmulo de débito técnico. | Product Owner, QA e Desenvolvedor. |


---

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
Gemini.

**Como foi utilizada:**  
A ferramenta foi utilizada para estruturar a matriz RACI de acordo com as regras estabelecidas (garantindo um único 'A' por linha) e auxiliar na formatação do documento no padrão Markdown solicitado.


**Como as respostas foram verificadas:**  
As respostas foram revisadas individualmente para garantir que as competências e responsabilidades refletissem a realidade prática de times ágeis e respeitassem a proposta de qualidade como responsabilidade compartilhada do projeto LocalEats.