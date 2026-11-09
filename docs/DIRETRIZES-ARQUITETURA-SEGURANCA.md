# Diretrizes de arquitetura, escopo e segurança — Galaxy Legacy

**Data da revisão:** 09/11/2026  
**Dispositivo-alvo:** Samsung Galaxy Tab A 7.0 (2016), SM-T280 / gtexswifi  
**Estado:** escopo aprovado pela pessoa responsável pelo projeto

Este documento registra as decisões atuais do projeto. Ele prevalece sobre ideias e protótipos exploratórios anteriores quando houver divergência.

## 1. Objetivo do Galaxy Legacy

O Galaxy Legacy será uma **experiência híbrida de interface construída como website**, acessada pelo Google Chrome no Android original.

O projeto não pretende transformar o tablet em um computador, criar uma distribuição Linux, substituir o Android por ChromeOS ou simular que o navegador é um sistema operacional completo.

A proposta atual é personalizar a experiência visual e a organização da interface web que o usuário acessa no tablet, mantendo o Android original como sistema operacional e preservando as funções nativas do aparelho.

A composição visual final ainda deverá ser detalhada. Não assumir que todos os elementos dos protótipos antigos — como desktop tradicional de PC, janelas independentes, gaveta de aplicativos ou loja — continuam sendo requisitos aprovados.

## 2. Regra permanente de segurança

A prioridade é sempre escolher a alternativa mais segura, simples e reversível que alcance o objetivo.

Por padrão:

- Preservar o firmware e a configuração original do Android.
- Não desbloquear o bootloader.
- Não obter root.
- Não modificar, substituir ou instalar ROM.
- Não gravar partições, alterar recovery ou modificar o kernel.
- Não realizar wipe ou restauração de fábrica para fins de desenvolvimento.
- Não desativar mecanismos de segurança nem serviços essenciais.
- Não sugerir procedimentos arriscados quando uma solução web ou configuração normal do Android for suficiente.

Uma modificação profunda só poderá ser reconsiderada se houver uma necessidade funcional comprovada, justificativa técnica clara, autorização expressa e plano de recuperação adequado. A existência de uma ROM mais recente, por si só, não justifica sua instalação.

## 3. Modelo de funcionamento: 100% online

A versão atual do Galaxy Legacy será inteiramente online.

- O website será hospedado em um serviço web e acessado pela internet.
- A conexão será necessária para carregar e utilizar o Galaxy Legacy.
- Conteúdo, páginas e funcionalidades deverão ser disponibilizados online.
- Não haverá requisito de funcionamento sem internet.
- Não será criada uma versão local para instalação, cópia por USB ou transferência por Bluetooth.
- Não desenvolver cache offline intencional, pacote offline, instalador local ou modo offline como parte do escopo.
- O cache normal e automático do navegador não deverá ser tratado como garantia de funcionamento offline.

O desenvolvimento deve priorizar uma aplicação web tradicional, leve e compatível com o Chrome do dispositivo. Recursos de PWA ou manifesto poderão ser usados somente quando contribuírem para a abertura do site pela tela inicial e forem comprovadamente compatíveis; não serão usados para criar uma estratégia offline.

## 4. Acesso pela tela inicial do Android

O caminho preferencial será usar o recurso do Chrome para adicionar o site à tela inicial.

A intenção é que o usuário tenha um ícone do Galaxy Legacy no launcher Android e possa abrir o website por ele, como uma entrada dedicada.

O manifesto web poderá declarar nome, ícones, URL inicial e modo de exibição independente, se o teste confirmar que o Chrome 43 do SM-T280 aceita esse comportamento. A documentação de exemplo do Chrome indica suporte a manifestos e ao fluxo “Add to homescreen” desde Chrome 39, mas isso não substitui o teste no aparelho real.

Devem ser diferenciados três comportamentos:

1. **Atalho comum:** cria um ícone que abre o endereço em uma aba normal do Chrome.
2. **Abertura independente:** o Chrome abre o site sem a interface normal de navegação, conforme o suporte do navegador e o manifesto.
3. **Aplicativo Android nativo:** APK instalado no sistema. Isso não faz parte do escopo.

Não prometer o segundo comportamento antes de testá-lo no SM-T280. Se o Chrome 43 oferecer apenas um atalho comum, esse resultado será avaliado sem tentar contornar as limitações do navegador.

## 5. Limites de personalização do dispositivo

O Galaxy Legacy poderá personalizar a aparência e o comportamento **da própria experiência web**: cores, tipografia, ícones do site, composição visual, navegação, páginas, conteúdo e apresentação responsiva.

Também poderá fornecer nome, ícone e endereço de início para o atalho do Chrome, dentro das capacidades confirmadas do navegador.

Um website não pode, por si só, substituir o launcher Android nem alterar livremente elementos globais do sistema, como:

- Papel de parede do Android.
- Tela de bloqueio.
- Barra de status e área de notificações do sistema.
- Barra de navegação do Android.
- Configurações de Wi-Fi, Bluetooth, som ou bateria.
- Permissões, serviços e aplicativos instalados.

Não apresentar controles ilustrativos do site como se controlassem essas funções reais. Alterações globais que dependam das configurações do Android permanecem fora da implementação web.

O objetivo é personalizar a experiência acessada pelo ícone do Galaxy Legacy, e não substituir ou modificar a aparência global do Android.

## 6. Política de aplicativos e conteúdo offline

O escopo atual **não prevê instalar aplicativos adicionais no tablet**.

O Galaxy Legacy não deverá incluir:

- Loja de APKs.
- Catálogo para instalar aplicativos Android.
- Gerenciador de pacotes.
- Importação de aplicativos por USB ou Bluetooth.
- Instalação de módulos locais.
- Biblioteca de aplicações offline.

Também não haverá leitor offline de arquivos nesta versão. Uma ideia futura de dispositivo ou experiência dedicada à leitura — semelhante a um Kindle — deverá ser tratada como projeto separado, caso seja retomada. Ela não é uma exceção ativa do Galaxy Legacy.

O Galaxy Legacy poderá apresentar conteúdo web de leitura quando conectado à internet, mas não deverá prometer abrir arquivos locais ou funcionar sem conexão.

## 7. Compatibilidade e implementação

O alvo prioritário continua sendo:

- Samsung Galaxy Tab A 7.0 (2016).
- Modelo SM-T280 / gtexswifi.
- Android 5.1.1.
- Google Chrome 43.0.2357.93.
- Tela de 800 × 1280.

O desenvolvimento deverá:

- Priorizar HTML semântico, CSS conservador e JavaScript compatível com a versão do Chrome.
- Evitar frameworks, bibliotecas e efeitos pesados sem necessidade.
- Utilizar hospedagem HTTPS.
- Manter o consumo de CPU, RAM e bateria baixo.
- Não depender de Service Workers, Cache API ou APIs modernas sem teste e necessidade.
- Distinguir suporte teórico de comportamento comprovado no tablet.
- Testar o site no Chrome 43 do próprio SM-T280 antes de declarar compatibilidade.

A implementação web não deverá exigir root, desbloqueio de bootloader, instalação de APK ou alteração de ROM.

## 8. Reinterpretação dos protótipos anteriores

Os protótipos v0.1 a v0.8 registram explorações visuais e interativas. Eles continuam fazendo parte do histórico, mas suas funcionalidades não são automaticamente requisitos da versão atual.

Em particular, ideias anteriores de desktop de PC, múltiplas janelas de miniaplicativos, gaveta de aplicativos, biblioteca de apps, pacotes locais e modo offline não devem ser tratadas como decisões atuais.

A direção atual prevalece:

1. Website 100% online.
2. Acesso pelo Chrome, preferencialmente por ícone na tela inicial.
3. Personalização visual da própria experiência web.
4. Android original preservado.
5. Nenhum aplicativo adicional obrigatório.
6. Nenhuma funcionalidade offline planejada.
7. Nenhuma modificação de ROM, bootloader, kernel ou partições.

## 9. Critério para reconsiderar qualquer mudança de sistema

Uma alteração profunda só poderá ser proposta quando:

- Uma limitação real impedir uma função importante do Galaxy Legacy.
- Uma solução web ou configuração comum do Android tiver sido investigada e se mostrado insuficiente.
- A mudança for tecnicamente compatível com o SM-T280.
- Os riscos, efeitos e limitações estiverem documentados.
- Existir um método de recuperação aplicável ao aparelho.
- A pessoa responsável pelo projeto autorizar expressamente a mudança.

Até que essas condições sejam atendidas, o Android original deve ser preservado.
