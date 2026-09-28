# Brief de design: site RG Massoterapia (Raiane Guimarães)

> **Como usar:** cole este documento no Claude Design e **anexe junto as imagens do Instagram** (@rg_massoterapiabjl): o post de sintomas, o "Super pacote Modeladora Power Detox", o "Seu corpo & sua autoestima", o "Ventosaterapia & bem-estar mental" e a foto da sala de atendimento. Elas são a referência visual principal.

---

## 1. Contexto do projeto

- **Cliente:** Raiane Guimarães, massoterapeuta, marca **RG Massoterapia**.
- **Local:** Bom Jesus da Lapa – BA *(confirmar)*.
- **Objetivo do site:** levar a pessoa a **agendar pelo WhatsApp**. Todo o layout gira em torno dessa ação.
- **Público:** mulheres e homens adultos da região com dores, estresse, ansiedade, cansaço ou interesse em estética corporal (modeladora, drenagem).
- **Sensação desejada:** acolhimento, calma, cuidado profissional e um toque de sofisticação. É um refúgio, não uma clínica fria.
- **Implementação final:** HTML puro + Tailwind CSS v4 (CLI). O design deve usar os tokens abaixo, que serão definidos via `@theme`.

---

## 2. Identidade visual (seguir fielmente as postagens)

### Paleta

| Token | Hex | Uso |
|---|---|---|
| `cream` | `#FBF6EE` | Fundo principal |
| `nude` | `#F3DFCB` | Seções alternadas e fundos de destaque (como no post do "Super pacote") |
| `sage` | `#6E8A68` | Botões, pílulas, ícones |
| `forest` | `#2F4A2B` | Títulos em serifa itálica |
| `gold` | `#B8923A` | Logo, folhas em traço, divisores finos |
| `ink` | `#4A4A48` | Texto corrido |

### Tipografia

- **Títulos:** *Playfair Display Italic* (ou *Fraunces Italic*), em verde `forest`, grandes e fluidos, como "seu corpo & sua autoestima" e "ventosaterapia & bem-estar mental". O **"&" em itálico** é marca registrada dos posts e deve aparecer nos títulos.
- **Chamadas curtas:** *Montserrat* em caixa alta com espaçamento aberto. Usar com moderação, só onde os posts usam (ex.: "CONHEÇA A TÉCNICA QUE…").
- **Texto corrido:** *Montserrat* 300–400, linhas com no máximo ~70 caracteres.

### Grafismos com folhas (obrigatório)

O site deve ter folhas em três camadas, como nas postagens:

1. **Folhas aquareladas** (eucalipto, trepadeira, samambaia) em verde suave, saindo pelos cantos das seções, parcialmente cortadas pela borda da tela.
2. **Folhas douradas em traço fino (line-art)**, como a costela-de-adão e as folhas finas do post de sintomas, em SVG com stroke `gold`.
3. **Silhuetas de folhas como marca d'água** no fundo, bem claras, como no post da modeladora.

Regras: as folhas **emolduram** o conteúdo, sem cobrir textos. No mobile, reduzir a quantidade e manter só as dos cantos.

### Elementos recorrentes das postagens

- **Pílulas verde-sálvia arredondadas** com texto claro ("Super pacote:", "Confira na legenda abaixo:").
- **Fotos em moldura de arco ou círculo**, ou com cantos bem arredondados.
- **Texto em curva** acompanhando a moldura da foto: "VOCÊ MERECE O MELHOR".
- **Monograma RG** dourado em selo circular.
- Muito respiro e composição leve, sem blocos pesados.

### O que evitar

- Visual de clínica/hospital (azul, branco frio, ícones médicos).
- Cards todos iguais com a mesma sombra cinza.
- Gradientes chamativos e animações em todas as seções. No máximo, **uma** entrada suave no hero.
- Excesso de dourado. Ele é detalhe, não cor principal.

---

## 3. Estrutura da página (ordem e conteúdo)

### 3.1 Header (obrigatório)
- Logo RG à esquerda.
- Menu: Massagens · Pacotes · Sobre · Contato.
- Botão **"Agendar no WhatsApp"** em `sage`, com ícone do WhatsApp.
- **Mobile:** menu hambúrguer, mas o botão do WhatsApp continua visível na barra.
- Fundo `cream`, fixo ao rolar com uma sombra sutil.

### 3.2 Hero em duas colunas (obrigatório)
- **Esquerda:**
  - Linha pequena: "Massoterapia em Bom Jesus da Lapa"
  - Título em serifa itálica: *"Seu corpo merece esse cuidado"*
  - Subtítulo: "Massagens relaxantes, terapêuticas e modeladoras em um espaço pensado para você desacelerar."
  - Botão: **"Agendar minha sessão"** (WhatsApp)
- **Direita (ilustração):** foto de massagem em **moldura de arco**, com o texto curvo "você merece o melhor" contornando a moldura, folhas aquareladas saindo por trás e uma folha dourada em traço sobreposta.
- **Mobile:** empilhar com a imagem abaixo do texto.

### 3.3 "Você tem algum desses sintomas?" (quiz interativo)
Reinterpretação do post de maior apelo do perfil.
- Título: *"Você tem algum desses sintomas?"*
- Chips clicáveis: Dores musculares · Insônia · Estresse · Cansaço · Ansiedade · Má postura · Tensão · Dores de cabeça.
- Ao marcar um ou mais chips, aparece: "Se a resposta foi sim para 1 ou mais, uma sessão pode te ajudar." e o botão **"Falar com a Raiane"**, que abre o WhatsApp com os sintomas escolhidos na mensagem.
- Fundo `cream` com folhas douradas em traço nos cantos, como no post original.

### 3.4 Tipos de massagem (obrigatório, 6 placeholders)
Grid 3×2 no desktop, 1 coluna no mobile. Cada item tem foto em cantos arredondados, nome em serifa itálica, descrição de 2 linhas, duração e o link "Quero essa".

1. **Relaxante:** alivia a tensão do dia a dia e acalma a mente.
2. **Modeladora:** manobras firmes que ajudam a contornar a silhueta.
3. **Drenagem linfática:** reduz inchaço e sensação de peso.
4. **Ventosaterapia:** solta a musculatura e favorece o bem-estar mental.
5. **Terapêutica / liberação miofascial:** foco em dores e pontos de tensão.
6. **Pedras quentes:** calor que relaxa profundamente.

Variar um pouco a composição (ex.: destacar a primeira ou alternar alturas) para não virar um "kit de cards" genérico.

### 3.5 Pacote em destaque
- Recriar o post **"Super pacote: Modeladora Power Detox"**: fundo `nude`, pílula verde "Super pacote:", nome grande dentro de uma pílula `sage`, foto em moldura de arco e texto curvo "você merece o melhor".
- Conteúdo: o que inclui, número de sessões e preço *(placeholders)*.
- Botão: **"Quero o pacote"**.

### 3.6 O espaço
- Galeria com 3–4 fotos da sala (referência: foto com plantas, prateleiras com "RELAX" e maca com manta clara).
- Frase: *"Um cantinho pensado para você desacelerar."*
- Layout assimétrico, com uma foto grande e duas menores.

### 3.7 Sobre mim (obrigatório)
- Foto da Raiane em moldura arredondada ou arco, com folha dourada contornando.
- Título: *"Prazer, eu sou a Raiane"*
- Texto em primeira pessoa (placeholder): trajetória, formação e por que escolheu cuidar de pessoas através do toque.
- Linha de selos de cursos e certificações *(placeholders)*.
- Monograma RG dourado como assinatura.

### 3.8 Como funciona a primeira sessão
Sequência real, então aqui a numeração faz sentido:
1. Você chama no WhatsApp
2. Conversamos sobre suas queixas e objetivos
3. Sessão personalizada para você
4. Orientações para continuar o cuidado em casa

Ícones em traço fino, conectados por uma linha orgânica em forma de ramo com folhas.

### 3.9 Depoimentos
- 3 citações de clientes *(placeholders)* com o nome e a massagem recebida.
- Aspas grandes em serifa itálica dourada.

### 3.10 Perguntas frequentes
Acordeão simples:
- Quanto tempo dura cada sessão?
- A ventosaterapia deixa marcas?
- Que roupa devo usar?
- Gestantes podem fazer massagem?
- Existem contraindicações?
- Quais as formas de pagamento?

### 3.11 CTA final
- Faixa em `sage` com folhas douradas em traço.
- Título em itálico claro: *"Você merece o melhor. Agende seu momento."*
- Botão claro: **"Agendar no WhatsApp"**.

### 3.12 Rodapé (obrigatório)
- Logo RG, endereço *(placeholder: Rua Exemplo, 123 – Centro, Bom Jesus da Lapa – BA)*, horário de atendimento *(placeholder)*.
- Links: Instagram @rg_massoterapiabjl e WhatsApp.
- Espaço para o mapa do Google.
- Folhas aquareladas subindo pelas bordas.
- Linha final: "© RG Massoterapia – Raiane Guimarães".

### Extra: botão flutuante
- Botão circular do WhatsApp fixo no canto inferior direito, em todas as telas.

---

## 4. Diretrizes de texto

- Tom acolhedor, próximo e simples, em português do Brasil.
- Falar de **alívio, bem-estar e cuidado**. Evitar promessas de cura ou resultados garantidos.
- Botões dizem exatamente o que acontece: "Agendar no WhatsApp", "Quero o pacote".
- Frases curtas. Cada texto faz um único trabalho.

---

## 5. Requisitos de qualidade

- Responsivo do mobile (360px) ao desktop (1440px). **Desenhar o mobile com o mesmo cuidado do desktop**, porque a maior parte do público virá do Instagram pelo celular.
- Contraste acessível, principalmente texto claro sobre `sage`.
- Foco visível em botões e links.
- Folhas decorativas não podem atrapalhar a leitura nem os cliques.

---

## 6. Entregáveis esperados do Claude Design

1. Página completa no desktop.
2. Página completa no mobile.
3. Estados do quiz de sintomas (nada marcado / sintomas marcados).
4. Lista final de tokens (cores, fontes, espaçamentos, raios) para levar ao `@theme` do Tailwind v4.
