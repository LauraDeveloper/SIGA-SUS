# SIGASUS

## Sistema Integrado de Gestão e Agendamento do SUS

O **SIGASUS** é um projeto acadêmico desenvolvido com Python com o objetivo de simular um fluxo de atendimento na Atenção Primária à Saúde, desde o cadastro do paciente até a classificação de risco, identificação da UBS de referência e geração de um comprovante de atendimento.

O projeto foi desenvolvido com foco em **lógica de programação, validação de dados, estruturas condicionais, funções, manipulação de arquivos e automação de processos**.

---

## Objetivo

O SIGASUS busca demonstrar como a tecnologia pode ser utilizada para organizar etapas do atendimento em uma Unidade Básica de Saúde (UBS), tornando o processo mais estruturado e facilitando o direcionamento do paciente.

O sistema realiza quatro etapas principais:

1. Cadastro e validação dos dados do paciente;
2. Triagem inicial e classificação de risco;
3. Agendamento da consulta de acordo com a prioridade;
4. Geração e armazenamento de um comprovante de atendimento.

---

## Funcionalidades

### 1. Cadastro do paciente

O sistema solicita informações básicas do paciente e realiza validações antes de concluir o cadastro.

São utilizados:

- Nome completo;
- CPF;
- Cartão Nacional de Saúde (CNS);
- Data de nascimento;
- Endereço;
- CEP;
- Telefone para contato.

### Validações implementadas

- Validação do CPF utilizando os dígitos verificadores;
- Validação do CNS com 15 dígitos;
- Validação da data de nascimento;
- Validação do CEP;
- Remoção de caracteres não numéricos de documentos e CEP.

---

## 2. Triagem e classificação de risco

O sistema possui uma etapa de triagem baseada nas cinco cores do **Protocolo de Manchester**:

| Cor | Classificação | Prioridade |
|---|---|---|
| 🔴 Vermelho | Emergência | Máxima |
| 🟠 Laranja | Muito urgente | Alta |
| 🟡 Amarelo | Urgente | Média |
| 🟢 Verde | Pouco urgente | Normal |
| 🔵 Azul | Não urgente | Rotina |

Os sintomas informados pelo usuário são normalizados para facilitar a comparação, incluindo a remoção de acentos.

> **Importante:** a classificação implementada no projeto é uma simulação educacional baseada em palavras-chave. Ela não substitui uma avaliação realizada por profissionais de saúde e não deve ser utilizada para decisões médicas reais.

---

## 3. Identificação da UBS

O sistema utiliza o CEP informado pelo paciente para tentar identificar o bairro e direcionar o usuário para uma **UBS de referência**.

O projeto possui um mapeamento de algumas faixas de CEP de **Campina Grande - PB**, associadas a UBS utilizadas no protótipo.

Quando o CEP não está contemplado no mapeamento, o sistema informa que a UBS de referência deve ser confirmada junto à Secretaria de Saúde.

---

## 4. Agendamento da consulta

Após a classificação de risco, o sistema determina uma data e horário de atendimento de acordo com a prioridade definida.

Exemplo de lógica utilizada:

- **Vermelho:** prioridade máxima;
- **Laranja:** prioridade alta;
- **Amarelo:** prioridade média;
- **Verde:** agendamento normal;
- **Azul:** consulta de rotina/acompanhamento.

O sistema também identifica a **Equipe de Saúde da Família** como responsável pelo atendimento no protótipo.

---

## 5. Comprovante de atendimento

Após o agendamento, o sistema:

- Exibe o comprovante no terminal;
- Registra os dados do atendimento;
- Informa a classificação de risco;
- Mostra a data e horário;
- Mostra a UBS indicada;
- Salva o comprovante em um arquivo de texto.

O histórico é armazenado no arquivo:

```text
comprovantes_sigasus.txt
