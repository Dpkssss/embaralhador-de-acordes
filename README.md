# Embaralhador de Acordes

Uma página para quem está aprendendo uma música no piano. Tem duas abas:

- **Inversões:** você digita os acordes (ou monta cada um escolhendo tônica, tipo e baixo), e ela mostra qual inversão usar em cada acorde para que o máximo de dedos fique na mesma tecla de um acorde para o outro.
- **Harmonizar melodia:** você grava ou escreve uma melodia, e ela descobre a tonalidade, sugere acordes, deixa você trocar cada um, toca o resultado e imprime a partitura.

## Inversões

- Aceita acordes digitados (`Am F C G`, `F#m7`, `A/D`) ou montados pelos botões
- Mostra cada posição num teclado, com as notas marcadas
- Escolhe o melhor caminho para a música inteira, não acorde por acorde
- Considera a volta do último acorde para o primeiro quando a música repete
- Funciona para acordes tocados com a mão esquerda ou com a direita
- Respeita o baixo dos acordes com barra (G/B, A/D)
- Permite fixar uma posição que você já sabe e recalcula o resto
- Toca cada acorde e a progressão inteira

## Harmonizar melodia

- **Entrada da melodia:**
  - Teclado MIDI (Chrome ou Edge): grava notas e ritmo depois de um compasso de contagem
  - Sem MIDI: grave só o ritmo tocando na barra de espaço (ou no botão grande) e depois escolha as notas no piano da tela; cada tecla preenche a nota selecionada e passa para a próxima
  - Escrever nota por nota clicando no piano
  - Importar um arquivo `.mid` (quando há várias trilhas, dá para escolher qual é a melodia)
- **Tonalidade:** detectada pelo perfil de Krumhansl-Schmuckler, com nível de confiança e alternativas. Também dá para escolher manualmente.
- **Acordes:** um por compasso, por meio compasso ou por tempo. Os candidatos incluem os acordes diatônicos, acordes com sétima, dominantes secundárias e empréstimos modais. A escolha considera quanto da melodia cabe em cada acorde (com mais peso nos tempos fortes) e as progressões mais comuns (V→I, ii→V, cadência final). Clique num acorde para ver as alternativas ordenadas, ouvir o trecho com cada uma e fixar a que preferir, ou digite qualquer outro acorde.
- **Ouvir:** melodia, acordes e metrônomo, com o compasso atual destacado.
- **Partitura:** melodia com cifras ou piano em duas pautas (a mão esquerda usa as inversões do Embaralhador). Imprime ou salva em PDF, e baixa o arquivo `.abc`.
- **Integração:** "Ver as inversões destes acordes" leva a progressão para a aba Inversões.

## Como usar

São arquivos estáticos, sem etapa de build. Abra o `index.html` no navegador ou sirva a pasta em qualquer servidor web. A partitura é desenhada com o [abcjs](https://github.com/paulrosen/abcjs) (licença MIT), incluído no arquivo `abcjs-basic-min.js`.

## Como a escolha funciona

Cada troca de acorde é pontuada pelo número de dedos que precisam sair da tecla. Em caso de empate, vence a opção em que a mão anda menos (em semitons). O melhor caminho para a progressão inteira é calculado por programação dinâmica.

Criado por Dario.
