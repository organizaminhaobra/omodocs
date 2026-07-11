# Documento de Requisitos do MVP — Organiza Minha Obra

> **Versão 1 — para revisão das sócias**
> Este documento é a evolução do BRD de vocês. Ele consolida, em linguagem de negócio, **o que o
> MVP vai fazer**, **o que fica de fora** e **os pontos que ainda precisam da decisão de vocês**.
> A ideia é que vocês leiam e apontem **se falta algo**.

---

## 1. Objetivo

Um aplicativo para **comunicação entre arquiteto e cliente durante a execução da obra**.

O arquiteto **registra a obra uma única vez** e o cliente **acompanha tudo em tempo real**. As
solicitações de pagamento ficam organizadas automaticamente, em um só lugar.

O sistema **não é um ERP de obras**, nem um software completo de orçamento ou planejamento — o foco
é tornar a comunicação simples e transparente.

---

## 2. Para quem é

- **Arquiteto / escritório** (usuário principal): alimenta todas as informações da obra.
- **Cliente** (usuário secundário): apenas **acompanha** — acesso somente leitura, não altera nada.

Observação importante: **escritório e arquiteto são a mesma conta** — cada conta gerencia
**várias obras de vários clientes**.

---

## 3. Como funciona (visão geral)

- O **arquiteto** cadastra a obra, o cronograma, os fornecedores, as compras da semana e publica
  atualizações no feed.
- O **cliente** recebe um convite, acessa o app e acompanha o andamento e o que precisa pagar.
- **Cada escritório enxerga apenas os seus próprios dados** — não há cruzamento entre escritórios.

---

## 4. Módulos do MVP

| Módulo | O que faz |
| --- | --- |
| **Login / Acesso** | Entrada do arquiteto e do cliente. |
| **Cadastro de obras e clientes** | O arquiteto cria a obra e vincula o cliente. |
| **Dashboard** | Visão rápida da obra: orçamento previsto, valor gasto, valor pendente, pendências da semana e última atualização. |
| **Cronograma (Gantt)** | Etapas da obra em barras, com data atual, dependências entre etapas e percentual de conclusão. O arquiteto edita; o cliente visualiza. |
| **Feed** | Linha do tempo com o andamento da obra (texto + fotos). O que o arquiteto publica aparece para o cliente. |
| **Acompanhamento Semanal** | Registro do que foi comprado na semana (material e mão de obra): data, tipo, item, fornecedor e valor. |
| **Pendências** | O que o cliente precisa pagar na semana, com total. O cliente só visualiza. |
| **Fornecedores** | Cadastro simples de fornecedores, para preencher as pendências automaticamente. |
| **Configurações** | Onde o arquiteto ajusta parâmetros da obra (ex.: dia de fechamento da semana). |
| **Notificações** | Central de avisos dentro do app. |

---

## 5. Fluxo da semana

- **Durante a semana:** o arquiteto atualiza o feed, registra compras e mão de obra, e ajusta o
  cronograma.
- **No dia de fechamento (padrão: sexta-feira):** o sistema organiza os lançamentos da semana, soma
  os valores e disponibiliza as pendências ao cliente. **Esse dia é configurável pelo arquiteto.**
- O cliente é **notificado** e vê o que precisa pagar.

---

## 6. Regras de negócio

**Cliente**

- *Pode:* visualizar dashboard, feed, pendências e acompanhamento semanal.
- *Não pode:* editar, adicionar, excluir, comentar, enviar comprovantes ou marcar pagamentos.

**Arquiteto / escritório**

- *Pode:* criar obras e clientes, editar o cronograma, cadastrar fornecedores, cadastrar compras e
  mão de obra, publicar no feed, anexar arquivos e editar qualquer informação.

**Pagamento acontece fora do sistema** (por enquanto), combinado por WhatsApp.

---

## 7. Decisões já tomadas

- **Uma conta por escritório/arquiteto**, gerenciando **várias obras de vários clientes**.
- **O cliente tem um único acesso** — mesmo que, no futuro, seja atendido por mais de um escritório
  que use o app (ele acompanha a obra vigente pelo mesmo acesso).
- **Convite do cliente:** o arquiteto cadastra o cliente e o **primeiro acesso** é enviado por
  **WhatsApp ou e-mail**. Depois disso, os **avisos ficam dentro do próprio app**.
- **Orçamento configurável** e **editável a qualquer momento**, com **registro de auditoria** das
  alterações (quem mudou e quando).
- **Relatório da obra** configurável, com opção de gerar uma visão geral e detalhada.
- **Histórico por semana:** é possível navegar pelas semanas anteriores da obra.
- **Acesso do cliente:** mantido **enquanto o arquiteto mantiver a conta ativa no app**. Os dados da
  obra ficam disponíveis e, após **2 anos**, são arquivados.
- **Fotos e documentos:** o app aceita **imagens** (fotos da obra, notas fiscais e orçamentos).

---

## 8. O que fica FORA do MVP

Para manter o MVP enxuto, **não entram** nesta primeira versão:

- **Não é um ERP** de obras, nem software completo de orçamento/planejamento.
- **Sem pagamento dentro do app** — o pagamento é feito por fora (o app não movimenta dinheiro).
- **Sem armazenamento de dados bancários nem dados de pagamento.** O app guarda dados pessoais e
  valores, mas **não** guarda contas bancárias nem chaves PIX. O pagamento é combinado
  **diretamente com o arquiteto, por fora do app**.
- **Sem upload de vídeos** nesta versão (apenas imagens).
- **Sem ações do cliente** dentro do sistema (ele apenas acompanha).
- **Sem planos e cobrança** nesta versão — a validação é feita com um único cliente; planos e a
  integração de pagamento virão numa fase seguinte.

---

## 9. Pontos em aberto — precisam da decisão de vocês

1. **Falta algo?**
   Ao ler os módulos e regras acima, **há alguma funcionalidade, informação ou situação do dia a dia
   de vocês que não está contemplada?**
