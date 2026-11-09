# Diretrizes de arquitetura, escopo e segurança — Galaxy Legacy

**Data de aprovação:** 09/11/2026  
**Dispositivo-alvo:** Samsung Galaxy Tab A 7.0 (2016), SM-T280 / gtexswifi  
**Estado:** diretrizes aprovadas pela pessoa responsável pelo projeto

Este documento registra decisões de escopo que prevalecem sobre ideias exploratórias anteriores quando houver divergência.

## 1. Objetivo correto do Galaxy Legacy

O Galaxy Legacy **não tem como objetivo transformar o tablet em um computador**, nem reproduzir integralmente um desktop de PC.

O objetivo é criar uma **experiência híbrida**, acrescentando uma camada própria de interface e organização sobre o Android original, sem substituir ou comprometer desnecessariamente o sistema existente.

O Android continua sendo o sistema operacional-base. O Galaxy Legacy deve coexistir com ele, respeitando seus recursos, limites e configurações.

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
- Não sugerir procedimentos arriscados quando uma solução web ou uma configuração comum do Android for suficiente.

Uma modificação profunda só poderá ser reconsiderada se houver uma necessidade funcional comprovada, uma justificativa técnica clara, autorização expressa e um plano de recuperação adequado. A existência de uma ROM mais recente, por si só, não justifica sua instalação.

## 3. Política de aplicativos

A intenção atual é **não instalar aplicativos adicionais no tablet**.

O Galaxy Legacy não deverá evoluir para uma loja de APKs, um catálogo de aplicativos Android, um gerenciador de pacotes ou uma plataforma que exija a instalação de vários programas.

A exceção que poderá ser avaliada separadamente é um leitor offline leve, destinado exclusivamente à leitura de arquivos locais. Essa exceção não está automaticamente aprovada como APK: primeiro devem ser avaliadas as possibilidades de leitura pelo próprio navegador e pelos recursos já existentes no Android.

Não planejar importação de pacotes de aplicativos internos, instalação de APKs em lote ou transferência de aplicativos como funcionalidade central.

## 4. Direção online: experiência 100% web

Quando conectado à internet, o Galaxy Legacy deverá priorizar uma experiência 100% web, acessada pelo Google Chrome.

Os sites poderão ser adicionados à tela inicial usando a funcionalidade do Chrome de criar atalhos para páginas. Esses atalhos devem ser tratados como formas de abrir sites, não como prova de que o Chrome transformou cada site em um aplicativo Android nativo.

A experiência online deve:

- Ser implementada com tecnologias web compatíveis com o Chrome instalado no SM-T280.
- Usar páginas e serviços web, sem exigir APKs adicionais.
- Permitir atalhos de sites na tela inicial quando o navegador oferecer essa função.
- Preservar o acesso normal ao Android e ao próprio Chrome.
- Ser leve, responsiva e adequada à tela de 800 × 1280.
- Não depender de recursos modernos de PWA, WebAPK ou Service Worker sem teste explícito no Chrome 43.0.2357.93.

A criação de atalhos na tela inicial deverá ser testada no dispositivo real antes de ser documentada como comportamento garantido. Caso o Chrome abra o site em uma aba normal, isso será aceito como comportamento do atalho; não se deve prometer uma janela independente ou modo standalone sem comprovação.

## 5. Direção offline: escopo limitado

O modo offline não precisa reproduzir todas as funções online.

A necessidade offline identificada é principalmente consultar arquivos locais, especialmente para leitura. Um leitor offline leve poderá ser investigado como exceção, depois de verificar quais formatos de arquivo são realmente necessários e quais recursos já estão disponíveis no Android ou no navegador.

Não ampliar o modo offline para uma coleção de aplicativos sem necessidade demonstrada.

## 6. O que significa “híbrido” neste projeto

“Híbrido” significa uma camada de interface e organização que combina a identidade e alguns comportamentos planejados do Galaxy Legacy com a continuidade do Android original.

Não significa:

- Converter o tablet em um PC.
- Substituir Android por ChromeOS.
- Criar uma distribuição Linux.
- Simular que páginas web são aplicativos Android nativos.
- Substituir controles reais do sistema por botões apenas decorativos.
- Exigir janelas flutuantes externas quando o sistema original não oferecer suporte.

Recursos de aparência, atalhos e navegação web devem ser distinguidos de integrações reais com o sistema. Wi-Fi, Bluetooth, notificações, permissões, armazenamento e outras funções Android não podem ser apresentados como controlados pelo Galaxy Legacy sem integração e teste reais.

## 7. Compatibilidade e implementação

O dispositivo prioritário continua sendo o SM-T280, Android 5.1.1, com Google Chrome 43.0.2357.93.

O desenvolvimento deve priorizar HTML, CSS e JavaScript conservadores, com baixo consumo de RAM, CPU, armazenamento e bateria. Recursos modernos não devem ser presumidos como disponíveis.

A inspeção de código, testes em computadores ou emuladores e validações automatizadas ajudam, mas não substituem testes no tablet físico.

A interface web pode ser desenvolvida e testada sem modificar o firmware. Nenhuma etapa do desenvolvimento web deve exigir root, desbloqueio de bootloader ou instalação de ROM.

## 8. Reinterpretação de ideias anteriores

As versões experimentais de desktop, janelas, gaveta de aplicativos, catálogo de aplicativos e instalação de módulos devem ser entendidas como explorações de interface, não como autorização para construir um computador ou instalar aplicativos Android.

As decisões atuais deste documento prevalecem:

1. Preservar o Android original.
2. Priorizar uma camada híbrida segura e reversível.
3. Priorizar a experiência online 100% web pelo Chrome.
4. Usar atalhos do Chrome para abrir sites pela tela inicial, se a compatibilidade for confirmada.
5. Considerar somente um leitor offline leve como possível exceção.
6. Não desenvolver loja de aplicativos nem sistema de instalação de APKs.

## 9. Critério para reconsiderar qualquer mudança de sistema

Uma alteração profunda só poderá ser proposta quando:

- Uma limitação real impedir uma função importante do Galaxy Legacy.
- Uma solução menos arriscada tiver sido investigada e se mostrado insuficiente.
- A mudança for tecnicamente compatível com o SM-T280.
- Os riscos, efeitos e limitações estiverem documentados.
- Existir um método de recuperação aplicável ao aparelho.
- A pessoa responsável pelo projeto autorizar expressamente a mudança.

Até que essas condições sejam atendidas, o Android original deve ser preservado.
