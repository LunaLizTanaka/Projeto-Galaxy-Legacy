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
