# Projeto Galaxy Legacy

Projeto para investigar, documentar e desenvolver sites e aplicativos web compatíveis com o tablet Samsung Galaxy Tab A (2016), modelo SM-T280.

## 1. Dispositivo-alvo

| Informação | Estado atual |
|---|---|
| Família/modelo | Samsung Galaxy Tab A (2016) |
| Código exato | SM-T280 |
| Sistema operacional | Android 5.1.1 |
| Navegador Chrome | Google Chrome 43.0.2357.93 |
| Motor Blink informado pelo Chrome | 537.36 (@196332) |
| Motor JavaScript V8 informado pelo Chrome | 4.3.61.22 |
| Outro navegador mencionado | Aplicativo identificado pela pessoa usuária como “Internet”/“Internet Explorer”; versão ainda não identificada |
| Versão do Samsung Internet | Ainda não confirmada |
| Resolução, memória e armazenamento | Ainda não verificados |

**Fonte da identificação:** fotografias das telas “Sobre o Google Chrome” e “Sobre o dispositivo”. A tela do Chrome informa Android 5.1.1 e SM-T280 Build/LMY47V; a tela de configurações identifica o aparelho como Galaxy Tab A (2016), modelo SM-T280.

## 2. Comportamento observado

- O tablet tem dificuldade para acessar alguns sites, enquanto outros ainda funcionam.
- O Google Chrome instalado é uma versão antiga (43.0.2357.93), em Android 5.1.1.
- A pessoa usuária prefere utilizar o Google Chrome. O Samsung Internet será considerado navegador secundário e poderá receber testes complementares.
- HTML continua sendo uma tecnologia utilizável; as limitações podem estar relacionadas à versão do Android, ao navegador, ao motor de renderização, a recursos de JavaScript/CSS ou a requisitos de segurança dos sites.
- Ainda não foi realizado um diagnóstico técnico completo no aparelho. As causas específicas das falhas permanecem em aberto.

## 3. Objetivos do projeto

Criar um conjunto de sites e aplicações web projetados e testados para o aparelho, incluindo:

1. **Portal principal:** página inicial com atalhos para os projetos e ferramentas.
2. **Navegador experimental:** interface web para organizar favoritos e acessar páginas. Inicialmente será apenas uma interface/aplicação web; não será um navegador nativo nem substituirá o navegador instalado.
3. **Biblioteca pessoal:** leitura de textos, anotações e organização de conteúdo.
4. **Ambiente de aplicativos:** ferramentas pessoais, interfaces de personagens, assistentes virtuais e animações leves.

## 4. Prioridade de navegadores\n\n- **Principal:** Google Chrome 43.0.2357.93. O desenvolvimento e os testes de aceitação devem priorizar essa versão instalada no tablet.\n- **Secundário:** Samsung Internet. A compatibilidade poderá ser verificada depois, sem comprometer a prioridade do Chrome.\n- Não presumir que os dois navegadores tenham o mesmo suporte a recursos.\n\n## 5. Diretrizes técnicas iniciais

Estas são hipóteses e critérios de compatibilidade a validar, não capacidades já confirmadas no tablet:

- Preferir HTML simples e semântico.
- Usar CSS conservador e layouts responsivos adequados à tela do aparelho.
- Evitar dependências grandes e frameworks modernos quando não forem necessários.
- Considerar JavaScript ES5 como baseline inicial de compatibilidade. O Chrome 43 usa V8 4.3.61.22, portanto recursos modernos não devem ser presumidos como disponíveis.
- Otimizar imagens e limitar animações, efeitos e consumo de memória.
- Não depender de PWA, Service Workers ou instalação como aplicativo até confirmar suporte.
- Verificar LocalStorage e oferecer alternativa quando necessário.
- Para requisições de rede, testar XMLHttpRequest e as restrições de HTTPS, certificados e CORS.
- Tratar áudio, vídeo, GIFs e outros recursos multimídia como funcionalidades que precisam de testes específicos.
- Priorizar páginas leves e, quando tecnicamente possível, recursos que continuem utilizáveis sem conexão.
- Não confundir compatibilidade visual com compatibilidade funcional: cada recurso precisa ser testado no navegador real.

## 6. Plano de diagnóstico

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

## 7. Informações ainda necessárias

Quando possível, registrar:

- Versão do Samsung Internet, caso seja possível encontrá-la em Configurações → Aplicativos → Internet → Informações do aplicativo.
- Resolução da tela e quantidade de memória RAM, se identificáveis.
- Exemplos de sites que funcionam e sites que falham, incluindo a mensagem de erro ou comportamento observado.

## 8. Critério de sucesso

Um projeto será considerado compatível somente depois de ser aberto e testado no próprio Galaxy Tab A (2016), SM-T280. Testes em emuladores ou inspeção de código podem ajudar, mas não substituem a validação no dispositivo físico.

## 9. Estado atual

**Fase:** levantamento inicial e planejamento.

**Confirmado:** modelo SM-T280, Galaxy Tab A (2016), Android 5.1.1, Google Chrome 43.0.2357.93, Blink 537.36, V8 4.3.61.22, dificuldade parcial de acesso a sites e objetivos gerais.

**Pendente:** resolução e RAM, exemplos concretos de sites com falha e execução do diagnóstico de compatibilidade. A versão do Samsung Internet é opcional, pois ele não é o navegador prioritário.


## 10. Investigação de ROM para o SM-T280

Foi criada uma documentação específica com a análise de árvores de dispositivo, versões LineageOS encontradas, o pacote AICP 12.1 não oficial publicado em outubro de 2026, riscos, requisitos de recuperação e compatibilidade planejada com o Galaxy Legacy.

- [Pesquisa de ROM para Galaxy Tab A SM-T280](docs/PESQUISA-ROM-SM-T280.md)

**Estado:** nenhuma ROM aprovada para instalação. A AICP 12.1 não oficial é apenas uma candidata para auditoria adicional; código-fonte e pacotes publicados não comprovam estabilidade no aparelho.


## 11. Diretriz atual de arquitetura e segurança

A direção aprovada é construir uma experiência híbrida sobre o Android original, sem transformar o tablet em um computador e sem modificar a ROM por padrão.

- Prioridade permanente: escolher a opção mais segura, simples e reversível.
- Não instalar aplicativos adicionais como parte do escopo normal.
- Priorizar uma experiência online 100% web pelo Chrome, usando atalhos de sites na tela inicial quando compatíveis.
- Considerar somente um leitor offline leve como possível exceção para leitura de arquivos locais.
- Não desenvolver loja de APKs ou sistema de instalação de aplicativos.
- Não desbloquear bootloader, obter root, gravar partições ou instalar ROM para implementar funções que possam ser atendidas pela camada web.

As decisões completas e as condições para reconsiderar mudanças profundas estão registradas em [Diretrizes de arquitetura, escopo e segurança](docs/DIRETRIZES-ARQUITETURA-SEGURANCA.md). Essas diretrizes prevalecem sobre ideias exploratórias anteriores quando houver divergência.


## 12. Escopo atual: website 100% online

A decisão atual é desenvolver o Galaxy Legacy como um website inteiramente online, acessado pelo Chrome no Android original.

- O site dependerá de conexão com a internet para funcionar.
- Não será criada versão offline, pacote local, leitor offline ou instalação de aplicativos.
- Uma futura experiência de leitura offline semelhante a um Kindle seria um projeto separado, não uma exceção ativa do Galaxy Legacy.
- O acesso preferencial será por um ícone do site adicionado à tela inicial do Android pelo Chrome, sujeito à validação no Chrome 43 do SM-T280.
- O objetivo visual é personalizar a própria experiência web, não substituir o launcher Android nem alterar configurações globais do sistema.
- Nenhuma ROM, root, desbloqueio do bootloader ou gravação de partições será necessária para desenvolver a versão web.

Ver [Diretrizes de arquitetura, escopo e segurança](docs/DIRETRIZES-ARQUITETURA-SEGURANCA.md), que prevalecem sobre ideias de protótipos antigos quando houver divergência.


## 13. Frente separada: manutenção do tablet e avaliação de ROM

A pessoa responsável também deseja melhorar o próprio SM-T280 e mantém aberta a possibilidade de modificar sua ROM. Essa investigação é separada do Galaxy Legacy Web, que permanece 100% online e não depende de alteração do Android.

A avaliação de ROM foi reaberta como possibilidade de manutenção do tablet. Antes de qualquer instalação, devem ser identificados os avisos exatos, investigadas suas causas e comprovada uma rota de recuperação específica para o SM-T280. Nenhuma ROM está aprovada e nenhuma alteração no sistema foi realizada.

Consulte [Pesquisa de ROM para SM-T280](docs/PESQUISA-ROM-SM-T280.md) e [Diretrizes de arquitetura, escopo e segurança](docs/DIRETRIZES-ARQUITETURA-SEGURANCA.md).
