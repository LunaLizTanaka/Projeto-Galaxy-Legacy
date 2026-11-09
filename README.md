# Projeto Galaxy Legacy

Projeto para investigar, documentar e desenvolver sites e aplicativos web compatíveis com o tablet Samsung Galaxy Tab A6, família de modelos SM-T280 / SM-T285.

## 1. Dispositivo-alvo

| Informação | Estado atual |
|---|---|
| Família/modelo informado | Samsung Galaxy Tab A6 |
| Códigos de modelo mencionados | SM-T280 / SM-T285 |
| Modelo exato do aparelho em uso | Ainda não confirmado |
| Navegador utilizado | Navegador de Internet da Samsung (Samsung Internet) |
| Versão do Android | Ainda não informada |
| Versão do Samsung Internet | Ainda não informada |
| Resolução, memória e armazenamento | Ainda não verificados |

**Importante:** SM-T280 e SM-T285 são variantes diferentes. A identificação exata deve ser confirmada em *Configurações → Sobre o dispositivo*. Não presumir que os dois modelos estejam sendo testados.

## 2. Comportamento observado

Informações relatadas pela pessoa usuária:

- O tablet tem dificuldade para acessar alguns sites.
- Alguns sites ainda podem ser acessados normalmente.
- O navegador informado é o Samsung Internet.
- HTML continua sendo uma tecnologia utilizável; as limitações podem estar relacionadas à versão do Android, ao navegador, ao motor de renderização, a recursos de JavaScript/CSS ou a requisitos de segurança dos sites.
- Ainda não foi realizado um diagnóstico técnico no aparelho. As causas específicas permanecem em aberto.

## 3. Objetivos do projeto

Criar um conjunto de sites e aplicações web projetados e testados para o aparelho, incluindo:

1. **Portal principal:** página inicial com atalhos para os projetos e ferramentas.
2. **Navegador experimental:** interface web para organizar favoritos e acessar páginas. Inicialmente será apenas uma interface/aplicação web; não será um navegador nativo nem substituirá o Samsung Internet.
3. **Biblioteca pessoal:** leitura de textos, anotações e organização de conteúdo.
4. **Ambiente de aplicativos:** ferramentas pessoais, interfaces de personagens, assistentes virtuais e animações leves.

## 4. Diretrizes técnicas iniciais

Estas são hipóteses e critérios de compatibilidade a validar, não capacidades já confirmadas no tablet:

- Preferir HTML simples e semântico.
- Usar CSS conservador e layouts responsivos adequados à tela do aparelho.
- Evitar dependências grandes e frameworks modernos quando não forem necessários.
- Considerar JavaScript ES5 como baseline inicial de compatibilidade, verificando recursos individualmente antes de adotar sintaxe ou APIs mais recentes.
- Otimizar imagens e limitar animações, efeitos e consumo de memória.
- Não depender de PWA, Service Workers ou instalação como aplicativo até confirmar suporte.
- Verificar LocalStorage e oferecer alternativa quando necessário.
- Para requisições de rede, testar XMLHttpRequest e as restrições de HTTPS, certificados e CORS.
- Tratar áudio, vídeo, GIFs e outros recursos multimídia como funcionalidades que precisam de testes específicos.
- Priorizar páginas leves e, quando tecnicamente possível, recursos que continuem utilizáveis sem conexão.
- Não confundir compatibilidade visual com compatibilidade funcional: cada recurso precisa ser testado no navegador real.

## 5. Plano de diagnóstico

Criar uma página de testes que verifique:

- Identificação do navegador e informações disponíveis sobre o ambiente.
- HTML, CSS, fontes, layout e dimensões da tela.
- Recursos de JavaScript e APIs disponíveis.
- LocalStorage: gravação, leitura e remoção de dados de teste.
- Reprodução de áudio e vídeo.
- GIFs e animações CSS.
- Requisições HTTP/HTTPS e comportamento de erros.
- Funcionamento sem conexão e persistência dos dados, quando suportados.
- Desempenho básico e comportamento com páginas mais pesadas.

Os resultados devem registrar navegador, versão do Android, data do teste e resultado de cada funcionalidade. Não declarar suporte sem teste no aparelho.

## 6. Informações ainda necessárias

Quando possível, registrar:

- Código exato do modelo: SM-T280 ou SM-T285.
- Versão do Android: *Configurações → Sobre o dispositivo → Informações do software*.
- Versão do Samsung Internet: menu/configurações → Sobre o Samsung Internet, se disponível.
- Resolução da tela e quantidade de memória RAM, se identificáveis.
- Exemplos de sites que funcionam e sites que falham, incluindo a mensagem de erro ou comportamento observado.

## 7. Critério de sucesso

Um projeto será considerado compatível somente depois de ser aberto e testado no próprio Galaxy Tab A6. Testes em emuladores ou inspeção de código podem ajudar, mas não substituem a validação no dispositivo físico.

## 8. Estado atual

**Fase:** levantamento inicial e planejamento.

**Confirmado:** família de aparelho informada, navegador utilizado, dificuldade parcial de acesso a sites e objetivos gerais.

**Pendente:** identificação exata da variante, versões do Android e Samsung Internet e execução do diagnóstico de compatibilidade.
