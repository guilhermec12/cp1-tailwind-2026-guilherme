# Checkpoint 1 — Tailwind

**Frontend Design · 2º semestre · Prof. Fábio Alencar**
Data: **quinta, 03/09/2026** · Janela: **08:00 às 09:40** · Individual

---

## O que é

Todos recebem o mesmo `index.html`: uma landing de evento, semântica e sem uma única classe. Seu trabalho é vesti-la com Tailwind seguindo a **carta de marca sorteada para o seu RM**.

A estrutura é a mesma para a turma inteira. O resultado tem que ser irreconhecível de um colega para o outro — é a carta que decide a cara da página, não o seu gosto.

## Sua carta

O sorteio foi gravado. **Sua carta está em `referencias/<seu RM>-<seu nome>/`**:

| | |
|---|---|
| `ficha.html` | a carta explicada: qual hex é fundo, qual é tinta, qual é destaque, as duas fontes renderizadas, o raio, a regra de composição, e os blocos de `<link>` e `@theme` prontos para colar |
| `ficha.png` | a mesma ficha em imagem, para consultar sem abrir o navegador |
| `mockup.png` | uma página finalizada naquela marca, como referência visual |
| `LEIA-ME.md` | o resumo em texto |

**O mockup é uma referência, não um gabarito.** Ele mostra um resultado possível. Você não precisa reproduzi-lo pixel a pixel, e não perde ponto por chegar num arranjo diferente — desde que a carta esteja lá e a regra de composição seja cumprida. Hierarquia, escala tipográfica, espaçamento e estados continuam sendo decisão sua, e é isso que a rubrica mede.

Ele vem só como imagem, de propósito. As classes que produzem aquele resultado são o que está sendo avaliado — escrevê-las é a prova.

Adapte os textos ao seu evento. "Nome do Evento" precisa virar o nome da sua carta, e o tom da cópia precisa combinar com os três adjetivos.

---

## Como rodar

**Não instale nada.** O Tailwind v4 já vem carregado como `<script>` no `index.html`:

```html
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4.3.3"></script>
```

Sem Vite, sem npm, sem build, sem terminal. Abra o arquivo no navegador (ou com o Live Server do VS Code), edite, salve, recarregue. O Tailwind recompila sozinho a cada classe nova.

Não troque essa linha nem acrescente outra forma de carregar o Tailwind.

---

## Regras

**1. O `<body>` é intocável.**
Não mude tags, não mude a ordem, não mude o aninhamento, não acrescente nem remova elementos. Você só encosta em duas coisas dentro do body: o atributo `class` e o texto visível.

**2. O `<head>` é seu.**
É lá que você carrega as fontes e declara os tokens. A área editável está marcada no arquivo.

**3. Os seis tokens são obrigatórios e os nomes não mudam.**

```css
@theme {
  --color-marca-50:  /* fundo    */;
  --color-marca-900: /* tinta    */;
  --color-marca-500: /* destaque */;
  --font-display:    /* títulos  */;
  --font-corpo:      /* corpo    */;
  --radius-card:     /* raio     */;
}
```

E precisam ser **usados através dos utilitários que eles geram**: `bg-marca-50`, `text-marca-900`, `bg-marca-500`, `font-display`, `font-corpo`, `rounded-card`. Declarar o token e não usar não conta.

**4. Nada de valor arbitrário.**
`bg-[#D4622A]`, `p-[13px]`, `text-[22px]` e afins estão proibidos. Se a cor ou o tamanho importam, viram token. Se não importam, cabem na escala do Tailwind.

**5. Nada de CSS solto.**
Nenhum atributo `style=""`, nenhuma regra CSS própria fora do bloco `@theme`. O `@theme` é o único lugar onde você escreve CSS.

**6. Mobile-first.**
Comece pelo layout de celular e use `sm:` `md:` `lg:` para crescer. Largura fixa em pixel não é responsividade.

**7. Estados.**
Todo link e todo botão precisa de `hover:` e de `focus-visible:`. O foco tem que ser visível sem depender de cor sozinha.

**8. Contraste.**
Texto sobre fundo precisa passar em WCAG AA (4.5:1 para texto normal). Quando a paleta da sua carta tem uma combinação que reprova, a `ficha.html` avisa num bloco **Atenção** e diz como contornar — em geral usando o destaque como campo, com a tinta por cima, em vez de como cor de texto.

---

## Entrega

Tudo pelo **assignment do Teams**, com **dois links**:

1. **Repositório no GitHub**, público, seu.
2. **Projeto publicado na Vercel**, no ar e abrindo.

O prazo do assignment é **09:40**. Depois disso ele fecha.

### Publicação

Como já vimos em aula: importe o repositório na Vercel, deixe o framework em *Other*, e publique. É um HTML estático, não precisa de configuração nenhuma. Publique **antes** de gastar os últimos minutos em detalhe visual — página bonita que não está no ar não conta.

### Histórico

- **Mínimo 3 pushes**, com pelo menos **30 minutos entre o primeiro e o último**. Um push só, no fim, vale penalidade.
- O primeiro push é o clone ainda sem estilo. Comece por ele.
- Nada de push depois das **09:40**. O que vale é o horário registrado pelo GitHub, não a data do commit na sua máquina.

### `ENTREGA.md`

Crie na raiz do repositório um arquivo `ENTREGA.md` com sua identificação e a declaração de IA:

```markdown
RM: 570000
Publicado em: https://seu-projeto.vercel.app
Carta: 07 · Vértice

IA: pedi ao Claude três variações de hierarquia para o hero. Usei a segunda,
mas troquei o text-4xl por text-5xl e refiz os breakpoints, porque o mobile
tinha ficado grande demais. O contraste do CTA eu resolvi na mão.
```

#### O que é a declaração de IA

**Usar IA é permitido neste checkpoint.** A declaração não é confissão e não tira ponto. Ela existe porque, na defesa de 10/09, eu vou perguntar sobre o seu código de qualquer jeito — a declaração só faz essa conversa começar honesta, em vez de você ter que fingir que digitou linha por linha.

**O que escrever:** duas ou três frases dizendo **o que você pediu**, **o que veio** e **o que você mudou ou descartou**. É a última parte que interessa. Se a IA gerou algo e você aceitou inteiro sem entender, escreva isso também — é uma resposta legítima, e vale mais do que inventar um ajuste que não houve.

**O que conta como usar IA:** Claude, ChatGPT, Gemini, Copilot completando classe no editor, IA do próprio navegador. Pedir para gerar classes, pedir paleta, pedir para explicar um erro, pedir para revisar acessibilidade — tudo conta. Não conta consultar a documentação do Tailwind, Stack Overflow ou os slides da aula.

**Se você não usou IA**, escreva exatamente isso: `IA: não usei.` Uma linha resolve — e leia a seção **Trilha sem IA** logo abaixo, porque essa linha vale pontos.

Comparando:

| | |
|---|---|
| **Serve** | "Pedi uma paleta a partir dos três hex da carta. Veio com `bg-amber-600` em tudo; troquei pelos tokens porque a regra 3 pede utilitário de token." |
| **Serve** | "Gerei o grid da lista de dados com IA e não entendi direito o `sm:grid-cols-3`. Deixei como veio." |
| **Não serve** | "Usei IA para ajudar." |
| **Não serve** | Colar quinze prompts sem dizer o que você fez com as respostas. |

O `ENTREGA.md` incompleto vale **−5**. Declaração vaga entra aqui.

## Defesa

Na aula de **10/09**, logo na abertura, **60 segundos por pessoa**. Abro o seu código e faço duas perguntas sobre ele — onde está tal token, por que tal utilitário e não outro. **Vale 35 dos 100 pontos** e a nota não fecha antes disso. Quem falta, perde os 35.

## Trilha sem IA

Quem fizer o checkpoint inteiro sem IA nenhuma pode reivindicar **+10 pontos**, escrevendo `IA: não usei.` no `ENTREGA.md`.

Reivindicar não é de graça: você faz a **defesa estendida**, de 90 segundos e três perguntas em vez de duas. A terceira é sempre de modificação ao vivo — *"adicione agora um breakpoint aqui"*, *"troque o raio de todos os botões de uma vez"*, *"inverta as cores desse botão"*. Você mexe no código na hora, comigo olhando.

**Como isso é pontuado**

- Sustentou a defesa estendida: **+10**, limitado a 100 no total.
- Não sustentou: perde os 10, e só. A nota base não leva punição extra por ter tentado.

Não existe penalidade formal para reivindicar e não sustentar — mas entenda o que acontece na prática: a pergunta de modificação ao vivo também conta para os 35 pontos da defesa normal. Quem escreveu o próprio código atravessa ela sem susto. Quem não escreveu sai pior nos 35 do que sairia se tivesse declarado o uso de IA e feito a defesa curta.

Ou seja: a trilha compensa quem realmente fez sozinho, e cobra caro de quem só disse que fez. Escolha com honestidade — o custo de declarar o uso de IA continua sendo **zero**.

---

## Avaliação

| Critério | Pontos |
|---|---:|
| Defesa de 60 segundos | 35 |
| `@theme` correto e tokens usados via utilitários | 20 |
| Flex/Grid e mobile-first, cumprindo a regra da sua carta | 20 |
| Fidelidade à carta: cor, tipografia, raio e tom da cópia | 15 |
| Estados (`hover`, `focus-visible`) e contraste AA | 10 |
| **Bônus — trilha sem IA, sustentada na defesa estendida** | **+10** |

Nota final limitada a 100.

**Penalidades**

| | |
|---|---:|
| Projeto não publicado, ou link publicado fora do ar | −15 |
| Estrutura do `<body>` alterada | −20 |
| Valor arbitrário ou CSS fora do `@theme` | −10 |
| Push único | −20 |
| `ENTREGA.md` ausente ou incompleto | −5 |
| Entrega fora da janela | −100 |

---

## O que entregar, em uma linha

Uma landing de evento no ar, que qualquer pessoa olha e diz de que marca ela é, construída só com utilitários do Tailwind sobre tokens que você declarou.
