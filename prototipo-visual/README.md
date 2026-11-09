# Galaxy Legacy — Protótipo Visual

Esta pasta reúne exclusivamente a ideia, o planejamento e os materiais do **protótipo visual** do Galaxy Legacy. Ela não representa um sistema operacional, uma ROM ou um launcher pronto para instalação.

## Objetivo

Criar uma demonstração visual leve para o Samsung Galaxy Tab A 7.0 (2016), modelo **SM-T280**, com abertura pelo navegador e sem exigir instalação no tablet.

## Conceito: desktop + Android

A experiência combina elementos de computador com a organização de uma tela inicial Android:

- Área de trabalho em tela cheia, adaptada ao espaço disponível.
- Páginas horizontais: deslizar para a esquerda/direita troca a página, sem precisar arrastar um cenário gigante para encontrar atalhos.
- Ícones de aplicativos diretamente na área de trabalho.
- Pastas para agrupar aplicativos e atalhos.
- Aplicativos demonstrativos abertos em janelas flutuantes independentes.
- Várias janelas podem permanecer abertas, ser movidas e organizadas; também podem ser minimizadas ou fechadas.
- Dock fixo para atalhos frequentes, recuperação de janelas e navegação entre páginas.
- Janelas abertas permanecem disponíveis ao trocar de página.

As janelas e aplicativos do protótipo são demonstrações visuais. Não representam aplicativos Android reais em execução dentro delas e não acessam os dados ou serviços do tablet.

## Identidade visual aprovada

- **Paleta:** D — Strawberry Milk.
- **Intensidade:** soft (pastéis suaves e claros).
- Cores de referência:
  - Rosa morango: `#F7DDE1`
  - Rosa leite: `#F3C4D0`
  - Pêssego/creme: `#F9E9D5`
  - Lilás: `#E8D5EA`
  - Malva: `#B68D9A`

Usar fundos suaves, detalhes discretos e contraste suficiente para leitura na tela de 800 × 1280.

## Requisitos de desempenho e compatibilidade

O hardware é limitado (1,5 GB de RAM e 8 GB de armazenamento interno). O protótipo deve priorizar fluidez e baixo consumo:

- Preferir HTML, CSS e JavaScript simples, sem frameworks ou dependências pesadas.
- Evitar vídeos de fundo, animações contínuas, blur, filtros pesados e transparências complexas.
- Preferir imagens estáticas, pequenas e otimizadas.
- Atualizar relógios e elementos dinâmicos apenas quando necessário.
- Evitar processos em segundo plano e trabalho desnecessário.
- Projetar para a resolução de 800 × 1280 e adaptar a interface a outras dimensões.
- Considerar o Chrome 43 identificado no tablet; evitar APIs e recursos modernos sem alternativa compatível.
- Não economizar recursos desativando ou prejudicando funções essenciais do Android.

## Limites desta pasta

Este espaço é dedicado ao protótipo visual. A investigação de ROMs, recuperação do sistema, desenvolvimento de aplicativos nativos e alterações no Android devem permanecer em suas próprias áreas de documentação.

O protótipo web não substitui o Android, não altera Bluetooth, Wi-Fi, notificações ou serviços do sistema e não aumenta a capacidade física do hardware.

## Versões

### v0.2 — conceito híbrido

- Área de trabalho em tela cheia.
- Duas páginas horizontais.
- Ícones de aplicativos e pastas.
- Janelas flutuantes independentes, com movimentação, minimização e fechamento.
- Dock fixo para atalhos e navegação.
- Arquivos locais entregues em HTML e ZIP.

### v0.1 — primeira exploração

Primeira demonstração de janelas flutuantes com cenário maior que a tela. Essa navegação foi substituída pela navegação por páginas horizontais; as janelas flutuantes foram mantidas.

## Regra de prioridade

**Desempenho, estabilidade e preservação das funções essenciais vêm antes de efeitos visuais ou quantidade de recursos.** Qualquer elemento opcional que prejudique a fluidez deverá ser simplificado ou removido.

## Validação

A sintaxe JavaScript do v0.2 foi inspecionada com Node.js. A tentativa de executar a página no Chromium deste ambiente foi bloqueada, portanto não foi possível concluir testes funcionais automatizados nesta etapa.

A compatibilidade com Chrome 43 e o desempenho no SM-T280 físico permanecem pendentes de validação. Não presumir compatibilidade antes desse teste.


## v0.3 — gestos de borda

- Removidas as frases de apresentação do topo.
- Arrastar da borda inferior para cima abre a gaveta com aplicativos e pastas.
- Arrastar da borda superior para baixo abre o painel rápido demonstrativo.
- Mantidas as janelas flutuantes, pastas, páginas horizontais e dock.
- Atalhos do painel rápido são ilustrativos e não alteram as configurações reais do Android.

JavaScript validado com `node --check`, HTML analisado com o parser padrão do Python e pacote ZIP verificado. A execução no Chromium automatizado foi bloqueada pela política do ambiente; não há ainda validação de interação no navegador nem teste no SM-T280 físico.


## v0.4 — configurações no gesto superior

- Arrastar do topo para baixo abre o painel **Configurações**, inspirado nas configurações rápidas do Android.
- Inclui atalhos demonstrativos, controles visuais de brilho/volume e botão para abrir os ajustes do Galaxy Legacy.
- Arrastar de baixo para cima continua abrindo a gaveta de aplicativos e pastas.
- Mantidas páginas horizontais, ícones, pastas, dock e janelas flutuantes.
- Os controles não alteram configurações reais do Android.

JavaScript verificado com `node --check`, HTML analisado pelo parser padrão do Python e verificações estáticas dos gestos concluídas; ZIP testado sem erros. A validação no Chrome 43 e no SM-T280 físico permanece pendente.


## v0.5 — fechar janelas arrastando para X

- Ao arrastar a barra de título, aparece um alvo **X — Solte aqui para fechar** na parte inferior.
- Soltar a janela sobre esse alvo fecha a janela/aba do protótipo.
- O X da própria barra de título e o botão de minimizar continuam disponíveis.
- Fechar a janela não desinstala nem remove o atalho do aplicativo; ele pode ser aberto novamente pela área de trabalho ou gaveta.

Verificações: HTML analisado pelo parser padrão do Python, JavaScript aprovado em `node --check`, rotinas do alvo/fechamento conferidas estaticamente e ZIP verificado sem erros. A interação ainda precisa ser testada em navegador real e no Chrome 43 do SM-T280.


## v0.6 — barra de janela simplificada

- Removidos os botões de minimizar (−) e fechar (×) de dentro das janelas.
- A barra de título exibe apenas o ícone e o nome do aplicativo e continua permitindo arrastar a janela.
- Para fechar, arraste a janela até o alvo X exibido na parte inferior e solte sobre ele.
- Aplicativos fechados continuam disponíveis na área de trabalho, gaveta e dock para serem abertos novamente.

Verificações: JavaScript aprovado em `node --check`, HTML analisado pelo parser padrão do Python, remoção dos controles confirmada estaticamente e ZIP testado sem erros. O teste real no navegador/Chrome 43 do SM-T280 ainda está pendente.
