# Especificação visual — Galaxy Legacy

## 1. Identidade visual aprovada

- **Paleta:** D — Strawberry Milk.
- **Intensidade:** soft (pastéis suaves e claros).
- **Direção estética:** interface delicada, acolhedora e kawaii, com uma mistura de desktop de computador e tela inicial Android.
- **Composição:** área de trabalho em tela cheia, páginas horizontais, ícones e pastas, além de janelas flutuantes independentes.

## 2. Cores oficiais

| Função | Nome | HEX |
|---|---|---|
| Cor principal | Rosa morango suave | `#F7DDE1` |
| Cor secundária | Rosa leite | `#F3C4D0` |
| Fundo claro / superfície | Pêssego-creme | `#F9E9D5` |
| Cor complementar | Lilás pastel | `#E8D5EA` |
| Ênfase / detalhes e contornos | Malva | `#B68D9A` |

Usar os tons claros como base e reservar o malva para detalhes, ícones, contornos e elementos que precisem de maior destaque. Textos devem manter contraste suficiente para leitura; não usar rosa ou lilás muito claros como cor de texto sobre fundos claros.

## 3. Conceito híbrido: desktop + Android

A interface não deve ser apenas uma grade de aplicativos nem apenas um desktop com cenário maior que a tela. O objetivo é combinar os dois modelos:

- **Área de trabalho em tela cheia:** ocupa a área disponível do tablet e se adapta à resolução. Não deve exigir arrastar um cenário maior que a tela para encontrar atalhos essenciais.
- **Páginas horizontais:** o usuário desliza para a esquerda ou direita, como nas telas iniciais do Android, para acessar outras páginas da área de trabalho.
- **Aplicativos e pastas:** ícones ficam diretamente na área de trabalho; pastas agrupam atalhos relacionados.
- **Janelas flutuantes:** tocar em um ícone abre o miniaplicativo em uma janela independente, mantendo a possibilidade de deixar várias janelas abertas ao mesmo tempo.
- **Organização de janelas:** janelas podem ser movidas, sobrepostas, organizadas lado a lado, minimizadas e fechadas. O dock permite abrir aplicativos e recuperar janelas minimizadas.
- **Dock fixo:** permanece acessível durante a troca de páginas e reúne atalhos frequentes e controles de navegação.
- **Persistência ao navegar:** trocar de página não deve fechar as janelas abertas; elas permanecem na camada de janelas da área de trabalho.

O cenário não deve depender de movimento livre em duas dimensões para acessar funções essenciais. A navegação principal entre áreas de trabalho será horizontal; o movimento livre fica reservado à organização das janelas.

## 4. Aplicação visual

- **Papel de parede:** fundos estáticos e leves, usando creme, rosa e lilás.
- **Ícones:** simples, reconhecíveis e com alvos de toque confortáveis.
- **Pastas:** aparência visual coerente com os ícones e identificação clara do conteúdo.
- **Janelas:** superfícies em rosa leite, pêssego-creme ou lilás, com contornos discretos em malva e barra de título para arrastar.
- **Barra superior e dock:** discretos, sem transparências pesadas.
- **Widgets:** poucos e úteis, sem competir com ícones e janelas.
- **Tipografia:** simples, legível e com contraste adequado à tela do SM-T280.

## 5. Desempenho como requisito obrigatório

A fidelidade visual nunca deve comprometer a fluidez do tablet. Priorizar sempre o menor consumo possível de RAM, CPU, bateria e armazenamento, preservando as funções essenciais do Android.

- Preferir imagens estáticas otimizadas; evitar vídeos, fundos animados, blur, sombras grandes e transparências complexas.
- Evitar animações contínuas; qualquer animação deve ser curta, discreta e dispensável.
- Atualizar widgets apenas quando necessário.
- Janelas e páginas inativas devem reduzir ao mínimo seu trabalho em segundo plano; não manter tarefas desnecessárias em execução.
- Não duplicar recursos nem carregar imagens e módulos que não estejam sendo utilizados.
- Não encerrar nem desativar serviços essenciais do Android para tentar economizar memória.
- Preservar Wi-Fi, Bluetooth, notificações, áudio, gerenciamento de bateria, armazenamento e demais funções originais.
- Preferir compatibilidade com o navegador principal informado para o tablet: Chrome 43 em Android 5.1.1. Validar os recursos no dispositivo real antes de declarar compatibilidade.

## 6. Dispositivo-alvo e limitações

- Samsung Galaxy Tab A 7.0 (2016), modelo SM-T280.
- Android original identificado: 5.1.1.
- Tela: 800 × 1280.
- Memória RAM informada no levantamento do projeto: 1,5 GB.
- Armazenamento interno informado: 8 GB, com espaço disponível muito limitado segundo relato da pessoa usuária.

O protótipo deve ser visualizado pelo navegador, sem exigir instalação no tablet. A interface deve ser leve e construída com recursos conservadores, considerando o Chrome antigo.

## 7. Critérios de aprovação visual

A interface será aprovada quando:
1. Utilizar a paleta Strawberry Milk em intensidade soft.
2. Ocupar a tela disponível e adaptar a composição à resolução.
3. Permitir trocar de página horizontalmente sem precisar deslocar o cenário em duas dimensões para acessar atalhos.
4. Apresentar aplicativos e pastas diretamente na área de trabalho.
5. Permitir manter múltiplas janelas flutuantes, movê-las e minimizá-las.
6. Manter dock e navegação acessíveis.
7. Priorizar fluidez e baixo consumo.
8. Não remover nem prejudicar funcionalidades essenciais do sistema.
9. Funcionar no Chrome do SM-T280 após teste no próprio tablet.

## 8. Estado

**Aprovado:** identidade visual Paleta D — Strawberry Milk, intensidade soft.

**Direção de interface definida:** híbrido entre desktop e Android, mantendo janelas flutuantes e acrescentando ícones, pastas e páginas horizontais. A área de trabalho ocupa a tela; não será necessário arrastar um cenário maior que a tela para localizar os aplicativos.

**Protótipo visual v0.1:** primeira demonstração com janelas flutuantes e cenário navegável por arraste. Foi substituída como direção principal pela composição híbrida descrita nesta especificação.

**Protótipo visual v0.2 criado (09/11/2026):** página HTML autônoma com duas páginas horizontais, ícones de aplicativos, pastas, dock fixo e miniaplicativos em janelas flutuantes. As janelas iniciais podem ser movidas, minimizadas ou fechadas; atalhos abrem janelas e pastas agrupam aplicativos. A cópia foi entregue como HTML e ZIP.

**Verificações realizadas:** inspeção sintática do JavaScript com Node.js. A tentativa de executar o protótipo em Chromium neste ambiente foi bloqueada pelo ambiente de execução; portanto, não há validação funcional de navegador concluída nesta etapa.

**Ainda não validado:** Chrome 43 e desempenho no SM-T280 físico. Não declarar compatibilidade antes do teste no próprio tablet.


## 9. Ajustes do protótipo visual v0.3 (09/11/2026)

- Removidos os textos de apresentação/slogan do topo da área de trabalho; mantidos a identidade Galaxy Legacy, o relógio e a área de trabalho.
- Adicionada uma gaveta de aplicativos e pastas, aberta ao arrastar da borda inferior para cima.
- Adicionado um painel rápido superior, aberto ao arrastar da borda superior para baixo, com relógio, data, notificações ilustrativas e atalhos visuais.
- Os atalhos de Wi-Fi, Bluetooth, Não perturbe e rotação são apenas demonstrações; não controlam serviços ou configurações Android.
- O painel de aplicativos permite iniciar os miniaplicativos em janelas flutuantes, sem eliminar a área de trabalho nem o dock.

**Validação v0.3:** JavaScript verificado com `node --check`; HTML analisado pelo parser padrão do Python; ZIP verificado sem erros. A execução automatizada no Chromium foi bloqueada pela política do ambiente (`ERR_BLOCKED_BY_ADMINISTRATOR`), portanto a interação por gestos ainda não foi testada em navegador real. Chrome 43 e SM-T280 físico permanecem pendentes.


## 10. Ajustes do protótipo visual v0.4 (09/11/2026)

- Gesto da borda superior para baixo abre o painel **Configurações** do Galaxy Legacy, inspirado nas configurações rápidas do Android.
- O painel inclui atalhos demonstrativos para Wi-Fi, Bluetooth, Não perturbe, rotação, modo avião e localização; controles visuais de brilho e volume; relógio/data; e acesso aos ajustes próprios do Galaxy Legacy.
- Gesto da borda inferior para cima continua abrindo a gaveta de aplicativos e pastas.
- A região de início dos gestos foi ampliada para facilitar o uso por toque.
- Os controles do painel são apenas visuais e não controlam serviços reais nem as configurações do Android.

**Validação v0.4:** JavaScript verificado com `node --check`; estrutura HTML analisada com o parser padrão do Python; verificações estáticas confirmaram os dois gestos e seus respectivos painéis; ZIP testado sem erros. Chrome 43 e SM-T280 físico permanecem pendentes de teste.


## 11. Ajuste do protótipo visual v0.5 — fechar janela por arraste (09/11/2026)

- Ao iniciar o arraste pela barra de título de uma janela, aparece um alvo destacado na parte inferior: **X — Solte aqui para fechar**.
- A janela é fechada quando é arrastada até a área do alvo e solta com o centro do alvo dentro dos limites da janela.
- O botão X da própria barra de título continua disponível como alternativa; minimizar também permanece disponível.
- Fechar remove somente a janela/aba em execução no protótipo. O atalho do aplicativo permanece na área de trabalho e na gaveta, podendo ser aberto novamente.

**Verificações v0.5:** estrutura HTML analisada pelo parser padrão do Python; JavaScript verificado com `node --check`; presença do alvo, rotina de detecção de sobreposição e rotina de fechamento conferidas estaticamente; ZIP testado sem erros. A validação do gesto por toque/mouse em navegador real e no Chrome 43 do SM-T280 permanece pendente.


## 12. Ajuste do protótipo visual v0.6 — barra de janela simplificada (09/11/2026)

- Removidos os botões internos de minimizar (−) e fechar (×) da barra de título das janelas flutuantes.
- A barra mantém somente o ícone e o nome do aplicativo e continua sendo a área para arrastar a janela.
- O fechamento permanece disponível pelo gesto de arrastar a janela até o alvo X inferior e soltá-la sobre ele.
- Os controles X para fechar os painéis de Configurações e Aplicativos são independentes e permanecem disponíveis.
- A gaveta e o dock continuam permitindo abrir aplicativos novamente após fechar suas janelas.

**Verificações v0.6:** JavaScript aprovado em `node --check`; HTML analisado com o parser padrão do Python; verificações estáticas confirmaram a remoção dos controles internos e a permanência do alvo de fechamento; ZIP verificado sem erros. Teste no navegador e no Chrome 43 do SM-T280 permanece pendente.


## 13. Ajustes do protótipo visual v0.7 — início sem janelas e ampliar por arraste (09/11/2026)

- A área de trabalho inicia sem aplicativos/janelas abertos; nenhum miniaplicativo é iniciado automaticamente ao carregar a página.
- O usuário abre um aplicativo ao tocar no respectivo ícone na área de trabalho, na gaveta ou no dock.
- Arrastar uma janela flutuante até o limite superior da área de trabalho e soltá-la amplia o aplicativo para ocupar toda a área de trabalho, mantendo a barra superior e o dock do Galaxy Legacy visíveis.
- Arrastar a barra superior de uma janela ampliada restaura a janela à geometria flutuante anterior e permite reposicioná-la.
- O gesto para fechar arrastando até o alvo X inferior permanece disponível.

**Verificações v0.7:** JavaScript aprovado em `node --check`; HTML analisado com o parser padrão do Python; verificações estáticas confirmaram ausência de abertura automática e presença da lógica de ampliar/restaurar; ZIP verificado sem erros. A interação visual ainda precisa ser testada em navegador real e no Chrome 43 do SM-T280.


## 14. Ajuste do protótipo visual v0.8 — aplicativos em tela cheia (09/11/2026)

- O shell do Galaxy Legacy ocupa toda a área de conteúdo disponível, com dimensões adaptáveis e sem rolagem da página.
- A área de trabalho continua híbrida: páginas horizontais, ícones, pastas, dock, gaveta de aplicativos e janelas flutuantes.
- A entrada continua limpa, sem aplicativos abertos automaticamente.
- Ao arrastar a barra superior de uma janela até o topo, o aplicativo entra em modo de tela cheia próprio. Nesse modo, desaparecem o desktop, as páginas, o dock e a moldura da janela; fica somente a interface do aplicativo ocupando a área disponível.
- O aplicativo maximizado reutiliza a mesma janela e os mesmos elementos editáveis. Ao voltar, o conteúdo permanece e a janela retorna à área de trabalho com a geometria flutuante anterior.
- A seta de retorno e o gesto de baixo para cima encerram o modo de aplicativo e retornam à área de trabalho. No desktop, o gesto inferior continua abrindo a gaveta de aplicativos.
- O gesto superior de cima para baixo abre Configurações rápidas também durante o modo de aplicativo.
- O pacote local inclui manifesto web com `display: fullscreen` e ícones, além de tentativa de usar a API de tela cheia após ação explícita do usuário quando disponível.

**Distinção de tela cheia:** CSS pode preencher o viewport da página, mas não pode obrigar o Chrome a esconder sua própria barra de endereço e seus controles. A experiência de aplicativo independente depende de publicação em HTTPS, suporte do navegador ao manifesto e adição à tela inicial; a API de tela cheia depende igualmente de suporte do navegador. Compatibilidade imersiva com Chrome 43/Android 5.1.1 não está confirmada.

**Verificações v0.8:** JavaScript validado com `node --check`, HTML analisado com o parser padrão do Python, manifesto JSON validado e pacote ZIP verificado. A execução visual no Chromium do ambiente não foi concluída; não há teste no SM-T280 físico.
