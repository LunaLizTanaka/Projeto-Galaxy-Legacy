# Especificação visual — Galaxy Legacy

## 1. Identidade visual aprovada

- **Paleta:** D — Strawberry Milk.
- **Intensidade:** soft (pastéis suaves e claros).
- **Direção estética:** interface delicada, acolhedora e kawaii, inspirada em desktops com janelas flutuantes.
- **Referência de composição:** cenário de desktop navegável, vários pequenos aplicativos em janelas independentes e elementos fixados nas bordas.

## 2. Cores oficiais

| Função | Nome | HEX |
|---|---|---|
| Cor principal | Rosa morango suave | `#F7DDE1` |
| Cor secundária | Rosa leite | `#F3C4D0` |
| Fundo claro / superfície | Pêssego-creme | `#F9E9D5` |
| Cor complementar | Lilás pastel | `#E8D5EA` |
| Ênfase / detalhes e contornos | Malva | `#B68D9A` |

Usar os tons claros como base e reservar o malva para detalhes, ícones, contornos e elementos que precisem de maior destaque. Textos devem manter contraste suficiente para leitura; não usar rosa ou lilás muito claros como cor de texto sobre fundos claros.

## 3. Aplicação na interface

- **Cenário / papel de parede:** preferir fundos estáticos e leves, com tons creme, rosa e lilás.
- **Janelas:** superfícies em rosa leite, pêssego-creme ou lilás, com contornos discretos em malva.
- **Barra superior e dock:** malva ou rosa leite, sem transparências pesadas.
- **Botões e estados selecionados:** rosa morango suave ou malva, mantendo contraste.
- **Widgets:** combinar as cores da paleta sem criar excesso de blocos ou elementos decorativos.
- **Tipografia:** simples, legível e com contraste adequado à tela do SM-T280.

## 4. Linguagem visual e interação

O conceito é um ambiente de desktop leve, não apenas uma grade convencional de ícones:

- Janelas flutuantes que podem ser movidas e organizadas.
- Possibilidade de manter mais de um painel visível.
- Cenário/área de trabalho que pode ser deslocado com gestos de arrastar.
- Painéis fixáveis nas bordas para permanecerem visíveis enquanto o cenário se move.
- Controles simples e alvos de toque adequados à tela de 7 polegadas.

## 5. Desempenho como requisito obrigatório

A fidelidade visual nunca deve comprometer a fluidez do tablet. Priorizar sempre o menor consumo possível de RAM, CPU, bateria e armazenamento, preservando as funções essenciais do Android.

- Preferir imagens estáticas otimizadas; evitar vídeos, fundos animados, blur, sombras grandes e transparências complexas.
- Evitar animações contínuas; qualquer animação deve ser curta, discreta e dispensável.
- Atualizar widgets apenas quando necessário.
- Painéis inativos devem reduzir ao mínimo seu trabalho em segundo plano; não manter tarefas desnecessárias em execução.
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

O protótipo inicial deve ser visualizado pelo navegador, sem exigir instalação no tablet. A interface deve ser leve e construída com recursos conservadores, considerando o Chrome antigo.

## 7. Critérios de aprovação visual

A interface será aprovada quando:
1. Utilizar a paleta Strawberry Milk em intensidade soft.
2. Manter textos e controles legíveis.
3. Apresentar janelas e painéis organizáveis sem poluir a tela.
4. Permitir explorar o cenário sem movimentar os painéis fixados.
5. Priorizar fluidez e baixo consumo.
6. Não remover nem prejudicar funcionalidades essenciais do sistema.
7. Funcionar no Chrome do SM-T280 após teste no próprio tablet.

## 8. Estado

**Aprovado:** identidade visual Paleta D — Strawberry Milk, intensidade soft.

**Protótipo visual v0.1 criado (09/11/2026):** foi produzida uma página HTML autônoma, sem dependências externas, com janelas móveis, minimização/restauração pelo dock, painéis fixáveis e navegação por arraste do cenário. A cópia para visualização foi entregue separadamente como arquivo HTML e pacote ZIP.

**Testes realizados nesta etapa:** verificações automatizadas em Chromium em resoluções desktop, tablet e celular; abertura de janelas, minimização/restauração, fixação/desfixação, navegação do calendário e movimentação do cenário foram exercitadas sem erros de JavaScript.

**Ainda não validado:** Chrome 43 e desempenho no SM-T280 físico. Os testes em Chromium não comprovam compatibilidade no tablet; essa validação permanece pendente e não deve ser presumida.
