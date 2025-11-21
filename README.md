# Sistema de Recomendação de Conteúdo Netflix 🎬

> **Projeto Aplicado III - Ciência de Dados** > Universidade Presbiteriana Mackenzie - 2025

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Status](https://img.shields.io/badge/Status-Concluído-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## 📌 Sobre o Projeto

Este projeto consiste no desenvolvimento de um **Sistema de Recomendação** para títulos da Netflix, utilizando técnicas de **Machine Learning** e **Processamento de Linguagem Natural (NLP)**.

Em um cenário de sobrecarga de conteúdo digital, o sistema visa atuar como uma ferramenta de curadoria eficiente. Além do entretenimento, o projeto possui um viés social alinhado ao **ODS 4 (Educação de Qualidade)** da ONU, propondo o uso da metodologia para recomendar documentários e conteúdos educacionais.

## 👥 Integrantes do Grupo

| Nome | RA |
|------|----|
| **Flávio Estevam Nogueira Andrade** | 10441572 |
| **Kaique Nascimento de Paula** | 24024831 |
| **Miguel Shiraishi** | 10431805 |
| **Moacyr Souza Barros** | 10441179 |


---

## 📚 Referencial Teórico

O projeto fundamenta-se nas principais abordagens de Sistemas de Recomendação estudadas na literatura:

1.  **Filtragem Baseada em Conteúdo (Content-Based):** Técnica adotada neste projeto. A similaridade é calculada através de atributos explícitos dos itens (sinopse, elenco, diretor). É eficaz para evitar o problema de *cold start* (novos itens), mas tende a ter menor diversidade (serendipidade).
2. **Filtragem Colaborativa:** Baseia-se no comportamento coletivo e histórico de interações (User-based ou Item-based), utilizando técnicas como fatoração de matrizes (SVD, ALS).
3. **Modelos Híbridos e Deep Learning:** Combinam múltiplas técnicas ou utilizam redes neurais profundas para capturar relações complexas e mitigar a esparsidade dos dados.

---

## 🛠️ Metodologia

O desenvolvimento seguiu o ciclo de vida de um projeto de Ciência de Dados, conforme detalhado abaixo:

### 1. Coleta e Preparação de Dados
* **Dataset:** Utilizou-se a base pública `netflix_titles.csv` com 6.234 títulos.
* **Limpeza:** Tratamento de dados faltantes em colunas como `director`, `cast` e `country`.
* **Engenharia de Features:** Criação da coluna `tags` através da concatenação de *director*, *cast*, *listed_in* (categorias) e *description*.
* **Normalização:** Conversão para minúsculas e remoção de espaços em nomes próprios (ex: "peter cullen" → "petercullen") para garantir que sejam tratados como tokens únicos pelo vetorizador.

### 2. Implementação do Algoritmo
* **Vetorização (TF-IDF):** O texto foi transformado em vetores numéricos usando *Term Frequency-Inverse Document Frequency*, penalizando termos muito comuns (stop words) e valorizando termos raros e descritivos.
* **Similaridade do Cosseno:** Calculou-se a proximidade angular entre os vetores para gerar a **Matriz de Similaridade** entre todos os títulos do catálogo.

---

## 📊 Resultados Obtidos

A avaliação foi qualitativa, focada na **coerência temática** das recomendações, dado a ausência de dados de interação de usuários (ratings).

### Exemplos de Recomendações

| Título de Entrada | Recomendações Geradas | Análise |
|-------------------|-----------------------|---------|
| **The Crown** | *Downton Abbey*, *Call the Midwife*, *The Frankenstein Chronicles* | Alta coerência com dramas históricos e produções britânicas. |
| **Squid Game** | *Alice in Borderland*, *Sweet Home*, *Kingdom* | Identificou produções asiáticas, thrillers e dramas intensos. |
| **Control Z** | *Elite*, *Who Killed Sara?*, *Rebelde* | Sugeriu séries hispano-americanas de suspense e drama teen. |
| **The Garden of Words** | *A Silent Voice*, *Your Name*, *Flavors of Youth* | Manteve-se fiel ao gênero anime e temas emocionais. |

### Pontos Fortes e Limitações
* **Fortes:** Coerência temática, distinção clara entre gêneros e eficiência computacional para prototipagem.
*  **Limitações:** Baixa diversidade (bolha de conteúdo) e dependência estrita da qualidade dos metadados textuais.

---

## 🏁 Conclusão

O projeto cumpriu o objetivo de desenvolver um sistema funcional de recomendação *Content-Based*. A abordagem mostrou-se eficaz para identificar similaridades semânticas sem a necessidade de histórico de usuários. Além disso, a metodologia mostrou-se aplicável para fins educacionais (ODS 4), servindo como base para sistemas de curadoria de aprendizado.

---

## 🚀 Melhorias e Trabalhos Futuros

Para evoluir este projeto de um protótipo acadêmico para um produto robusto, mapeamos as seguintes etapas:

### 1. Melhorias no Modelo
* **Representação Semântica:** Substituir o TF-IDF por modelos de linguagem avançados como **Word2Vec**, **Doc2Vec** ou **Sentence-BERT** para capturar contextos profundos além da correspondência exata de palavras.
* **Refinamento de Texto:** Implementar técnicas de *stemming* ou *lemmatization* e testar *n-grams* (bigramas) para enriquecer o contexto.

### 2. Evolução do Sistema
* **Abordagem Híbrida:** Combinar a filtragem baseada em conteúdo com filtragem colaborativa para resolver problemas de esparsidade e aumentar a diversidade das sugestões.
* **Métricas Quantitativas:** Implementar métricas de ranking como *Precision@K*, *Recall@K* e *NDCG* assim que dados de interação estiverem disponíveis.

### 3. Expansão e Produto
* **Multimodalidade:** Integrar análise de imagens (pôsteres) e áudio (trilhas sonoras) no cálculo de similaridade.
* **MLOps:** Implementar pipeline de produção com API, monitoramento de performance e dashboards.
* **Foco Educacional:** Adaptar o algoritmo para plataformas de museus virtuais ou bases de conhecimento, priorizando conteúdo cultural.

---

## 📑 Referências

* **BURKE, R.** *Hybrid recommender systems: Survey and experiments*. User Modeling and User-Adapted Interaction, 2002.
* **GÓMEZ-URIBE, C. A.; HUNT, N.** *The Netflix Recommender System*. ACM, 2016.
* **RICCI, F. et al.** *Recommender Systems Handbook*. Springer, 2022.
* **ZHANG, S. et al.** *Deep learning based recommender system*. ACM Computing Surveys, 2019.

---

## ▶ Link da apresentação no YouTube

https://www.youtube.com/watch?v=3exQAmMsKhY
