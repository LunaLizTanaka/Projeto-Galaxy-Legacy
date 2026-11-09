# Galaxy Legacy — Protótipo Visual

Esta pasta reúne exclusivamente a ideia, o planejamento e os materiais do **protótipo visual** do Galaxy Legacy. Ela não representa, por enquanto, um sistema operacional, uma ROM, nem um launcher pronto para instalação.

## Objetivo

Criar uma demonstração visual navegável de um ambiente de trabalho para o tablet Samsung Galaxy Tab A 7.0 (2016), modelo **SM-T280**, sem exigir instalação no tablet. A primeira forma de visualização deverá ser uma página web leve, aberta pelo navegador Chrome.

## Conceito da interface

O protótipo deverá explorar uma área de trabalho com:

- Janelas flutuantes que permitem visualizar vários miniaplicativos na mesma tela.
- Janelas que possam ser movidas e organizadas pelo usuário.
- Uma área de trabalho/cenário maior que a tela, navegável por gestos de arrastar.
- Alguns painéis ou janelas que possam ficar fixados nas bordas enquanto o cenário se movimenta.
- Uma barra de atalhos e áreas para widgets e aplicativos demonstrativos.
- Uma aparência de ambiente próprio, e não apenas uma grade convencional de ícones.

As janelas do protótipo serão demonstrações visuais. Não se deve sugerir que aplicativos Android reais estejam sendo executados dentro delas.

## Identidade visual aprovada

- **Paleta:** D — Strawberry Milk.
- **Intensidade:** soft (pastéis suaves e claros).
- Cores de referência:
  - Rosa morango: `#F7DDE1`
  - Rosa leite: `#F3C4D0`
  - Pêssego/creme: `#F9E9D5`
  - Lilás: `#E8D5EA`
  - Malva: `#B68D9A`

Usar fundos suaves, detalhes discretos e contraste suficiente para leitura na tela de 800 × 1280. A paleta deve ser aplicada sem depender de efeitos gráficos pesados.

## Requisitos de desempenho e compatibilidade

O hardware é limitado (1,5 GB de RAM e 8 GB de armazenamento interno). O protótipo deve priorizar fluidez e baixo consumo:

- Preferir HTML, CSS e JavaScript simples, sem frameworks ou dependências pesadas quando não forem necessários.
- Não usar vídeo de fundo, animações contínuas, blur, filtros pesados ou transparências complexas.
- Preferir imagens estáticas, pequenas e otimizadas.
- Atualizar relógios e elementos dinâmicos apenas quando necessário.
- Evitar processos em segundo plano e trabalho desnecessário.
- Projetar para a resolução de 800 × 1280 e testar a responsividade.
- Considerar o Chrome 43 identificado no tablet; evitar APIs e recursos modernos sem alternativa compatível.
- Não economizar recursos desativando ou prejudicando funções essenciais do Android.

## Limites desta pasta

Este espaço é dedicado ao protótipo visual. A investigação de ROMs, recuperação do sistema, desenvolvimento de aplicativos nativos e alterações no Android devem permanecer em suas próprias áreas de documentação.

O protótipo web não substitui o Android, não altera Bluetooth, Wi-Fi, notificações ou serviços do sistema e não aumenta a capacidade física do hardware.

## Etapas sugeridas

1. Criar um mockup estático da área de trabalho.
2. Validar a hierarquia visual, cores, tamanhos e legibilidade.
3. Implementar interação leve para mover e organizar janelas.
4. Implementar navegação por arraste do cenário, mantendo os painéis fixados quando aplicável.
5. Testar no Chrome disponível e reduzir qualquer recurso que cause lentidão.
6. Só depois de aprovado, decidir separadamente se vale transformar o conceito em um launcher nativo.

## Regra de prioridade

**Desempenho, estabilidade e preservação das funções essenciais vêm antes de efeitos visuais ou quantidade de recursos.** Qualquer elemento opcional que prejudique a fluidez deverá ser simplificado ou removido.
