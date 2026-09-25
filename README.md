# Embaralhador de Acordes

Uma página para quem está aprendendo uma música no piano. Você digita os acordes (ou monta cada um escolhendo tônica, tipo e baixo), e ela mostra qual inversão usar em cada acorde para que o máximo de dedos fique na mesma tecla de um acorde para o outro.

## O que ela faz

- Aceita acordes digitados (`Am F C G`, `F#m7`, `A/D`) ou montados pelos botões
- Mostra cada posição num teclado, com as notas marcadas
- Escolhe o melhor caminho para a música inteira, não acorde por acorde
- Considera a volta do último acorde para o primeiro quando a música repete
- Funciona para acordes tocados com a mão esquerda ou com a direita
- Respeita o baixo dos acordes com barra (G/B, A/D)
- Permite fixar uma posição que você já sabe e recalcula o resto
- Toca cada acorde e a progressão inteira

## Como usar

É um único arquivo HTML, sem dependências nem etapa de build. Abra o `index.html` no navegador ou sirva a pasta em qualquer servidor web.

## Como a escolha funciona

Cada troca de acorde é pontuada pelo número de dedos que precisam sair da tecla. Em caso de empate, vence a opção em que a mão anda menos (em semitons). O melhor caminho para a progressão inteira é calculado por programação dinâmica.

Criado por Dario.
