# Projeto: Portal Acadêmico Universitário (SIGAA)

Este repositório contém o documento de Especificação de Requisitos de Software (ERS) para o projeto SIGAA, como parte da atividade acadêmica da disciplina de Introdução a Ciência da Computação.

## 👥 Equipe

* Ana Beatriz Vila Nova Ribeiro
* Ana Luísa Vieira da Silva
* João Lucas Cosme
* Yuri Neves de Arruda Cabral
* Zaque Mateus Neves da Silva

---

# Levantamento de Requisitos — Portal Acadêmico Universitário (SIGAA)

## 1. Introdução

### 1.1 Propósito

Este documento tem como objetivo descrever os requisitos funcionais e não funcionais do Sistema Integrado de Gestão Acadêmica (SIGAA). O sistema será utilizado para centralizar, registrar e gerenciar as atividades acadêmicas centrais da instituição, como matrículas, lançamento e consulta de notas, registro de frequência e comunicação oficial.

### 1.2 Escopo do Sistema

O SIGAA permitirá que alunos realizem suas matrículas online, consultem seu desempenho (notas e frequência) e recebam avisos. Permitirá aos professores o lançamento desses dados e a comunicação com suas turmas. O sistema gerará relatórios acadêmicos e documentos básicos (ex: declaração de vínculo). O sistema não fará a gestão financeira (cobrança de mensalidades), mas deverá ser capaz de exportar dados para o sistema financeiro da instituição.

### 1.3 Definições e Abreviações

* **SIGAA:** Sistema Integrado de Gestão Acadêmica
* **IES:** Instituição de Ensino Superior
* **SGA:** Sistema de Gestão Acadêmica (banco de dados central ou sistema ERP da instituição.)
* **LGPD:** Lei Geral de Proteção de Dados
* **API:** Interface de Programação de Aplicações

### 1.4 Referências

* Lei nº 13.709/2018 – Lei Geral de Proteção de Dados (LGPD)
* Regulamentos e Normas Acadêmicas da Instituição (Regimento Geral, Calendário Acadêmico)
* Diretrizes de Acessibilidade (ex: WCAG - Web Content Accessibility Guidelines)

## 2. Descrição Geral

### 2.1 Perspectiva do Produto

O SIGAA é um sistema web que substituirá processos manuais, descentralizados ou presenciais (como matrícula em formulário de papel, diários de classe físicos e murais de aviso físicos). Ele se integrará ao SGA existente para se tornar o principal ponto de autoatendimento e comunicação entre alunos, professores e a administração acadêmica.

### 2.2 Funções Principais

* Gerenciamento de matrícula online (solicitação, aprovação, ajuste).
* Lançamento e consulta de notas e frequências.
* Publicação e visualização de avisos (gerais e por disciplina).
* Emissão de documentos acadêmicos básicos.

### 2.3 Tipos de Usuários

* **Aluno:** Realiza matrícula, consulta notas, frequência, histórico e avisos; emite documentos.
* **Professor:** Lança notas e frequência de suas turmas; publica avisos e materiais de apoio.
* **Secretaria Acadêmica:** Gerencia o calendário, publica avisos gerais, processa solicitações, gera relatórios institucionais.
* **Coordenação de Curso:** Homologa matrículas, acompanha o desempenho acadêmico dos alunos do curso, valida dados.
* **Administrador (TI):** Gerencia perfis de usuário, permissões, configurações do sistema e monitora a integridade.

### 2.4 Restrições

O sistema deve obedecer rigorosamente aos prazos definidos no Calendário Acadêmico (ex: janelas para matrícula, janelas para lançamento de notas).

O sistema deve manter o histórico acadêmico de alunos egressos (desligados ou formados) por tempo indeterminado, conforme regulamentação do MEC/IES.

O cálculo da média final e da situação (aprovado/reprovado) deve seguir exatamente a fórmula definida no regimento da IES.

### 2.5 Suposições e Dependências

Supõe-se que a IES possui um Sistema de Gestão Acadêmica (SGA) ou banco de dados centralizado que contém os dados cadastrais de alunos, professores, cursos e disciplinas. O SIGAA dependerá de integração com este sistema.

O sistema depende de conexão estável com a internet para todos os tipos de usuários.

## 3. Requisitos Funcionais

| Código | Descrição | Prioridade |
| :--- | :--- | :--- |
| RF01 | O sistema deve permitir a autenticação de usuários (Aluno, Professor, Secretaria, etc.) por meio de ID (matrícula/login) e senha. | Alta |
| RF02 | O sistema deve permitir que o aluno solicite matrícula online nas disciplinas ofertadas para seu curso/período, dentro do prazo estipulado. | Alta |
| RF03 | O sistema deve permitir que o professor lance as notas (parciais e finais) dos alunos de suas respectivas turmas. | Alta |
| RF04 | O sistema deve permitir que o professor registre a frequência (presenças e faltas) dos alunos em suas turmas. | Alta |
| RF05 | O sistema deve permitir que o aluno consulte seu boletim detalhado, exibindo notas por avaliação e o percentual de frequência em cada disciplina. | Alta |
| RF06 | O sistema deve possuir um mural de avisos para a Secretaria Acadêmica publicar comunicados gerais visíveis a todos os alunos | Média |
| RF07 | O sistema deve permitir que o professor publique avisos específicos para os alunos de uma determinada turma. | Média |
| RF08 | O sistema deve permitir que a Coordenação de Curso ou Secretaria Acadêmica aprove, rejeite ou ajuste as solicitações de matrícula dos alunos. | Média |
| RF09 | O sistema deve permitir que o aluno emita documentos automatizados, como Declaração de Vínculo (Atestado de Matrícula) e Histórico Escolar parcial. | Média |
| RF10 | O sistema deve enviar notificações (via e-mail ou no portal) ao aluno quando uma nova nota for lançada ou um novo aviso for publicado. | Média |
| RF11 | O sistema deve registrar logs de todas as ações críticas (ex: alteração de nota, trancamento de matrícula) para fins de auditoria. | Alta |

## 4. Requisitos Não Funcionais

| Código | Categoria | Descrição | Prioridade |
| :--- | :--- | :--- | :--- |
| RNF01 | Segurança | O sistema deve estar em conformidade com a LGPD, garantindo que dados pessoais e acadêmicos sejam armazenados e transmitidos de forma criptografada. | Alta |
| RNF02 | Desempenho | O sistema deve suportar picos de 5.000 usuários simultâneos durante os primeiros dias da janela de matrícula, com tempo de resposta máximo de 5 segundos por requisição. | Alta |
| RNF03 | Usabilidade | A interface deve ser responsiva, adaptando-se para uso funcional em dispositivos móveis (smartphones e tablets). | Alta |
| RNF04 | Confiabilidade | O sistema deve ter uma disponibilidade de 99,5% durante o período letivo. | Alta |
| RNF05 | Segurança | O acesso ao sistema deve ser protegido por uma política de senhas fortes e possuir um mecanismo seguro de recuperação de senha (ex: via e-mail institucional). | Alta |
| RNF06 | Acessibilidade | O sistema deve seguir as diretrizes de acessibilidade (WCAG 2.1 Nível AA) para garantir o uso por pessoas com deficiência (ex: leitores de tela). | Média |
| RNF07 | Manutenibilidade | O sistema deve ser desenvolvido com uma arquitetura baseada em APIs (REST) para facilitar a integração com sistemas legados (SGA) e futuros (Financeiro, Biblioteca). | Média |
