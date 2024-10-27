# Desafio: Dashboard de Vendas com Power BI utilizando Star Schema

## Contexto

Este repositório contém a resolução do desafio "Dashboard de Vendas com Power BI utilizando Star Schema," parte do bootcamp oferecido pela **NTT Data** em parceria com a **DIO**, no módulo "Modelagem de Dados com Power BI." O enunciado completo do desafio está no arquivo [Descrição do Desafio - Star Schema - Professor.docx](https://academiapme-my.sharepoint.com/:w:/g/personal/renato_dio_me/EW6ICs-FWeJPjRJt5mhdTFABzxYtZl87MzYPc6s2N1aO7Q?rtime=_k5Bdx323Eg).

## Estrutura e Desenvolvimento do Projeto

### Modelagem de Dados

Para a modelagem do banco de dados, utilizei o **SQL Workbench** para criar tanto o diagrama inicial quanto a resolução em **Star Schema**. Essa abordagem visual facilitou a compreensão das relações entre as tabelas e da transformação das tabelas em **Dimensões** e **Tabela Fato**.

- **Diagrama Base**: Repliquei a estrutura fornecida no enunciado, adicionando campos de data que ajudam a visualizar melhor as interações entre as tabelas e como elas seriam utilizadas na transição para o esquema estrela.
  
- **Diagrama Star Schema**: Realizei uma série de simplificações e modificações para seguir a modelagem em esquema estrela:
  - A tabela **Aluno** foi removida, e as informações essenciais foram distribuídas entre as demais tabelas.
  - Pré-requisitos foram movidos para a tabela **D_Disciplina**.
  - A tabela **D_Curso** foi diretamente associada à tabela **Professor**, evitando uma modelagem tipo "Snowflake."

Assim, a **Tabela Fato** (F_Professor) ficou composta por:
- ID (chave substituta da tabela),
- Nome do professor,
- Chaves estrangeiras para as tabelas **D_Disciplina**, **D_Curso**, **D_Data**, e **D_Departamento**.

### Estrutura de Data

A tabela **D_Data** foi configurada para suportar informações temporais sobre o início e fim das atividades dos professores, incluindo semestre e ano de oferta, proporcionando maior granularidade e flexibilidade nas análises de dados baseadas em tempo.

![Imagem do Esquema Estrela e Diagramas](link_para_imagem)
