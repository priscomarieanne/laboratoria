# Análise da Thread — Performance de Playlists Editoriais

## 1. Problema de negócio central

A diretoria quer entender se o investimento em **curadoria editorial de playlists** realmente gera valor para a empresa ou se os resultados observados são consequência de outros fatores, como tendências de mercado ou características das próprias músicas.

O objetivo é produzir uma análise baseada em dados que ajude a justificar (ou revisar) o investimento na curadoria e orientar decisões para o próximo ciclo de orçamento.

---

## 2. Perguntas de negócio (priorizadas pela VP)

### Prioridade 1 — Responder se a curadoria gera valor

1. A curadoria editorial gera impacto real no desempenho das músicas (streams), ou o sucesso ocorre independentemente da curadoria?

### Prioridade 2 — Identificar sinais precoces para tomada de decisão

2. Existem sinais iniciais que permitam identificar, nos primeiros dias/semanas, quais músicas têm maior potencial de sucesso?

3. A presença em múltiplas playlists do Spotify está associada a um maior número de streams?

4. A presença em múltiplas plataformas (Spotify, Apple Music, Deezer e Shazam) está relacionada ao sucesso da música?

### Prioridade 3 — Encontrar padrões que apoiem a estratégia editorial

5. Músicas que entram nos charts do Spotify possuem mais streams do que aquelas que não entram?

6. Características da música influenciam o volume de streams?
   - Número de artistas
   - Gênero principal
   - País de origem

7. O momento do lançamento (ano e mês) influencia o volume acumulado de streams?

---

## 3. Bases de dados disponíveis

| Tabela | Objetivo | Principais colunas mencionadas |
|--------|----------|--------------------------------|
| **Track_in_spotify** | Desempenho das músicas dentro do Spotify | `track_id`, nome da música, artista(s), quantidade de artistas, gênero principal, país principal, data de lançamento (ano, mês e dia), número de playlists do Spotify em que aparece, posição/presença em charts do Spotify e número total de streams |
| **Track_in_competition** | Desempenho da mesma música em outras plataformas | `track_id`, presença em playlists e charts do Apple Music, Deezer e Shazam |

### Chave de relacionamento

- **`track_id`** (presente nas duas tabelas), permitindo cruzar as informações entre elas.

---

## Limitações dos dados

As limitações mencionadas na thread são:

- Não há informação sobre **investimento editorial por faixa**, o que impede medir diretamente o retorno financeiro da curadoria.
- Não existe **histórico temporal de streams (dia a dia)**, limitando análises de evolução do desempenho e identificação precisa de sinais precoces.
- Caso a análise indique necessidade de informações adicionais, será preciso solicitar novas fontes ao time de **Data Engineering**.
- Deve-se ter cuidado para **não confundir correlação com causalidade**, principalmente ao avaliar o impacto da presença em playlists sobre o volume de streams.
