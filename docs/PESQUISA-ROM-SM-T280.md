# Investigação de ROM — Galaxy Tab A 7.0 (SM-T280)

**Data da verificação:** 09/11/2026  
**Dispositivo-alvo:** Samsung Galaxy Tab A 7.0 (2016), **SM-T280**, codinome **gtexswifi**  
**Objetivo:** encontrar uma ROM Android específica e suficientemente confiável para servir de base ao Galaxy Legacy.  
**Estado da decisão:** **nenhuma ROM aprovada para instalação**.

> Esta documentação diferencia arquivos de código, pacotes de instalação e evidências de funcionamento. Uma árvore de dispositivo ou uma publicação ZIP não comprovam, por si só, que uma ROM seja estável ou segura para o tablet.

## 1. Identificação do dispositivo

| Item | Informação |
|---|---|
| Modelo | Samsung Galaxy Tab A 7.0 (2016) |
| Código exato | **SM-T280** |
| Codinome | **gtexswifi** |
| SoC | Spreadtrum SC7730SW / plataforma SC8830 |
| CPU | Quad-core 1,30 GHz, Cortex-A7, ARMv7 |
| GPU | Mali-400 MP2 |
| RAM | 1,5 GB |
| Armazenamento interno | 8 GB |
| Tela | 7 polegadas, 800 × 1280 |
| Android original informado | 5.1.1 |

Os valores acima também aparecem no README da árvore de dispositivo. **Não confundir SM-T280/gtexswifi com SM-T285**, que é outra variante. Não usar pacote de T285, LTE ou outro codinome.

Fonte de dispositivo: [README da árvore gtexswifi](https://github.com/underscoremone/android_device_samsung_gtexswifi/blob/cm-14.1/README.md).

## 2. Resultado principal: AICP 12.1 não oficial

Foi localizado um pacote binário de ROM publicado no GitHub:

- Projeto de releases: https://github.com/Lost-Entrepreneur439/gtexswifi-releases
- Publicação: https://github.com/Lost-Entrepreneur439/gtexswifi-releases/releases/tag/2026-10-13
- Nome do arquivo: `aicp_gtexswifi_n-12.1-UNOFFICIAL-20261013.zip`
- Publicado em: **13/10/2026**
- Tamanho informado: **309.084.502 bytes** (aproximadamente 309 MB decimais)
- SHA-256 informado pelo GitHub para o arquivo: `fbeada8b002bf71975c8e8af3219e9c360f1df3123eb00ce76b66c52f88b1e89`
- Nota de lançamento: “Update to unofficial September 2026 security patches”.
- A publicação identifica explicitamente o pacote como **UNOFFICIAL**. O contador observado durante a consulta era de 22 downloads; isso não representa aprovação nem comprovação de uso bem-sucedido.

Árvore de dispositivo associada encontrada: https://github.com/Lost-Entrepreneur439/device_samsung_gtexswifi/tree/n7.1.

O arquivo `aicp.mk` dessa árvore declara:
- `PRODUCT_NAME := aicp_gtexswifi`
- `PRODUCT_DEVICE := gtexswifi`
- `PRODUCT_MODEL := SM-T280`
- Fabricante Samsung.

O `BoardConfig.mk` também declara `TARGET_OTA_ASSERT_DEVICE := SM-T280,gtexswifi`. Isso é uma correspondência importante entre a configuração de compilação e o tablet-alvo.

### Limitações e riscos desta publicação

1. A versão é identificada como AICP 12.1 e usa a branch `n7.1`, ou seja, pertence à geração **Android 7.1 Nougat**. Não é um Android moderno.
2. Os patches de segurança de setembro de 2026 são uma afirmação da nota de lançamento. A extensão, origem e cobertura desses patches **não foram auditadas**.
3. A árvore de dispositivo foi criada em setembro de 2026, mas seu README ainda contém instruções antigas para compilar LineageOS 14.1. Isso indica documentação reaproveitada/desatualizada e exige cautela.
4. O pacote ZIP não foi baixado nem inspecionado internamente nesta investigação. Seu conteúdo, instalador, assert de modelo, partições alteradas e assinatura não foram verificados.
5. Não foi encontrada evidência independente suficiente de testes prolongados no SM-T280, estabilidade, funcionamento de todos os componentes ou procedimento confiável de recuperação.
6. O hash SHA-256 é um identificador de integridade publicado pelo GitHub. Ele deverá ser comparado com o arquivo obtido, mas não prova que o autor ou o conteúdo sejam confiáveis.

**Avaliação:** é a pista mais concreta encontrada porque existe um pacote de instalação publicado com nome correspondente ao codinome do SM-T280 e uma árvore que declara o modelo correto. Ainda assim, é uma ROM comunitária não oficial e **não está aprovada para instalação**.

## 3. LineageOS 14.1 — árvore original de dispositivo

Repositório principal: https://github.com/underscoremone/android_device_samsung_gtexswifi

- Branch padrão: `cm-14.1`.
- Base indicada no README: LineageOS 14.1 / Android 7.1.
- A árvore declara o destino `SM-T280,gtexswifi` e contém arquivos de configuração de compilação, kernel, recuperação, áudio, Bluetooth, Wi-Fi, gráficos e câmera.
- O README ensina a compilar a ROM com uma árvore de código e dependências adicionais. Não é um guia para instalar um ZIP pronto.
- A compilação depende de outros repositórios específicos, inclusive kernel, vendor proprietário e componentes Spreadtrum.
- O README avisa que a compilação do TWRP deve ser feita separadamente: há uma limitação entre a imagem de kernel usada no boot e a usada na recuperação.

Estado observado no GitHub:
- Último commit da árvore de dispositivo: **27/12/2021**.
- Último envio do kernel vinculado: **27/12/2021**.
- Último envio do vendor vinculado: **12/02/2021**.
- Os repositórios de dispositivo, kernel e vendor consultados não apresentavam releases de ROM.
- O repositório de dispositivo tinha uma questão aberta perguntando se uma versão mais nova da LineageOS seria possível. A resposta aponta para outro projeto AOSP, mas o endereço exato citado não foi localizado durante a consulta.

Fontes:
- [Device tree](https://github.com/underscoremone/android_device_samsung_gtexswifi)
- [Kernel](https://github.com/underscoremone/android_kernel_samsung_gtexswifi)
- [Vendor](https://github.com/underscoremone/proprietary_vendor_samsung_gtexswifi)
- [Questão sobre versões mais novas](https://github.com/underscoremone/android_device_samsung_gtexswifi/issues/2)

**Avaliação:** código-fonte direcionado ao aparelho, mas antigo e sem pacote de instalação publicado nesse conjunto de repositórios. Não é a primeira opção para continuar a busca por uma ROM pronta.

## 4. Outras árvores de versões posteriores

A busca por `gtexswifi` encontrou árvores de dispositivo com nomes de branches mais recentes. Elas são pistas de desenvolvimento, não ROMs prontas.

| Projeto | Branch encontrada | Estado observado |
|---|---|---|
| [test-one9/android_device_samsung_gtexswifi](https://github.com/test-one9/android_device_samsung_gtexswifi/tree/lineage-16) | `lineage-16` (Android 9) | Contém produto `lineage_gtexswifi` e modelo SM-T280; último commit observado em 19/07/2026. README ainda ensina o fluxo antigo 14.1. Nenhuma release de ROM encontrada nesse repositório. |
| [gtexswifi-lineage/android_device_samsung_gtexswifi](https://github.com/gtexswifi-lineage/android_device_samsung_gtexswifi/tree/lineage-15.1) | `lineage-15.1` (Android 8.1) | Atualizações observadas em setembro de 2026, mas documentação continua apontando para 14.1 e não foi localizado o makefile de produto esperado nessa branch. Nenhuma release de ROM encontrada. |
| [ChasTechProjects/android_device_samsung_gtexswifi](https://github.com/ChasTechProjects/android_device_samsung_gtexswifi/tree/lineage-17.1) | `lineage-17.1` (Android 10) | Árvore antiga, com último commit observado em 05/12/2020. README ainda descreve 14.1. Nenhuma release de ROM encontrada. |

Essas branches não foram compiladas, e os arquivos não foram testados no tablet. A presença de uma branch chamada `lineage-16` ou `lineage-17.1` não comprova que o sistema inicialize, que todos os drivers funcionem ou que exista uma imagem instalável.

## 5. O que a ROM precisa preservar

O Galaxy Legacy não deve sacrificar funções essenciais para obter aparência de desktop. Antes de aprovar uma ROM, será necessário encontrar evidências de funcionamento no SM-T280 para:

- Inicialização, tela sensível ao toque e rotação.
- Wi-Fi e Bluetooth.
- Áudio, microfone e alto-falantes.
- Câmera frontal e traseira.
- Sensores, localização/GPS e gerenciamento de energia.
- Carregamento, suspensão e retomada.
- Armazenamento interno e cartão microSD.
- USB e conexão com um computador.
- Notificações e serviços básicos do Android.

A árvore contém configurações para vários desses componentes, mas isso não é prova de que funcionem em uma compilação final.

## 6. Compatibilidade com o Galaxy Legacy

A ideia é usar o Android como base e o Galaxy Legacy como interface personalizada. O protótipo HTML é apenas uma referência visual; a implementação final deve ser um aplicativo Android/launcher, com integração progressiva ao sistema.

Arquitetura desejada:
1. **Launcher Galaxy Legacy:** tela inicial, páginas, ícones, pastas e dock; abre aplicativos Android instalados.
2. **Janelas:** janelas flutuantes reais exigem suporte do sistema a freeform/multi-window ou alterações compatíveis no framework e no gerenciador de janelas. Split-screen não é automaticamente equivalente a janelas livres sobrepostas.
3. **Tela cheia:** aplicativos podem usar a área imersiva quando o Android e o aplicativo permitem.
4. **Configurações e notificações:** integrar serviços reais do Android; não substituir Wi-Fi, Bluetooth ou notificações por simples controles ilustrativos.
5. **Personalização visual:** aplicar a paleta Strawberry Milk, intensidade soft, sem animações e efeitos caros para o hardware.

A AICP 12.1 encontrada é da geração Android 7.1. Ela pode servir de base para um launcher, mas a presença de janelas flutuantes reais não foi confirmada. Isso deve ser um teste técnico independente antes de escolher essa ROM.

## 7. Critérios obrigatórios antes de considerar instalação

Nenhuma instalação deve ser iniciada até todos estes pontos serem resolvidos:

- Confirmar que o pacote é explicitamente destinado ao **SM-T280/gtexswifi**, não ao SM-T285.
- Inspecionar o ZIP e o script de instalação, identificar exatamente quais partições serão alteradas e conferir o destino permitido.
- Verificar o SHA-256 do arquivo baixado contra o digest publicado pelo GitHub.
- Identificar a recuperação compatível e comprovar que há um caminho de restauração para o firmware original do SM-T280.
- Encontrar relatos independentes de funcionamento no mesmo modelo, com testes de Wi-Fi, Bluetooth, áudio, câmera, carregamento, suspensão, toque e armazenamento.
- Preparar e verificar um backup completo antes de qualquer alteração.
- Confirmar que há espaço de armazenamento suficiente e que o processo não depende de serviços pagos.

**Não instalar por enquanto.** A existência de um ZIP, mesmo com o nome correto, não substitui uma análise interna, verificação da recuperação, backup e comprovação de estabilidade.

## 8. Conclusão e decisão atual

- **AICP 12.1 não oficial (Android 7.1):** pacote ZIP correspondente ao codinome do tablet encontrado; é o candidato que merece auditoria adicional, mas ainda não está aprovado.
- **LineageOS 14.1 (Android 7.1):** árvore de código específica e antiga, sem release binária encontrada nos repositórios centrais consultados.
- **LineageOS 15.1/16.0/17.1:** foram encontradas árvores de desenvolvimento, mas não pacotes instaláveis comprovados; não devem ser chamadas de ROM funcional.
- **Galaxy Legacy:** deve ser construído como launcher Android independente da ROM, com integração adicional ao sistema apenas depois de a base ser escolhida e validada.

A prioridade continua sendo uma ROM gratuita, específica para SM-T280, estável e recuperável. Se não houver evidência suficiente, manter o Android original é mais seguro do que instalar uma compilação experimental.

## 9. Limites desta investigação

A verificação foi feita nos metadados, arquivos, branches, commits e releases públicos do GitHub em 09/11/2026. A página XDA anteriormente identificada não foi revalidada nesta etapa. O conteúdo binário do ZIP AICP também não foi inspecionado, não houve compilação, teste em emulador ou teste físico. As conclusões indicam o estado da evidência disponível, não garantias de funcionamento.


## 10. Levantamento adicional de relatos fornecido pela pessoa usuária (09/11/2026)

A pessoa usuária compartilhou mensagens e resultados de pesquisa produzidos pelo **Gemini**, que realizou buscas complementares em fóruns e repositórios, incluindo XDA Developers e AndroidFileHost. As conclusões abaixo são registradas como **informações fornecidas pelo Gemini**, ainda não auditadas diretamente por esta investigação.

### LineageOS 14.1 — build indicada pelo Gemini como funcional

- ROM indicada: **LineageOS 14.1 Unofficial**, Android 7.1.2 Nougat.
- Desenvolvedor associado: `_mone`.
- Build indicada como última estável: `lineage-14.1-20210209-UNOFFICIAL-gtexswifi.zip`.
- Pasta AndroidFileHost informada: https://androidfilehost.com/?w=files&flid=165161
- Thread XDA já identificada no levantamento do projeto: https://forum.xda-developers.com/t/rom-lineageos-14-1-samsung-galaxy-tab-a-7-0-sm-t280-gtexswifi.4158061/

**Relatos apresentados pelo Gemini:**
- Wi-Fi e Bluetooth funcionais.
- Áudio e microfone funcionais.
- Câmera nativa pode falhar na captura; uso de câmera de terceiros, como Open Camera, foi citado como alternativa.
- Suspensão e tela funcional; foram mencionadas correções relacionadas ao carregamento com a tela desligada.
- Boa estabilidade após a configuração inicial, sem reinicializações aleatórias ou travamentos frequentes nos relatos consultados.
- Suporte para formatar cartão microSD como armazenamento interno na build indicada.

**Estado da evidência:** esses pontos ainda precisam ser ligados às mensagens exatas, datas, versão de build e experiência de usuários do modelo SM-T280. Não foram reproduzidos em teste independente nesta investigação. Até essa conferência, tratar “estável” como avaliação comunitária relatada, não como garantia.

### Resultado apresentado pelo Gemini para outras versões

A pesquisa compartilhada pelo Gemini não encontrou builds funcionais confirmadas para:
- AICP 12.1;
- LineageOS 15.1;
- LineageOS 16.0;
- LineageOS 17.1.

Essa conclusão deve ser interpretada como **ausência de ROM funcional confirmada nos fóruns consultados pela pessoa usuária**, e não como prova de inexistência de qualquer árvore de código.

### Reconciliação com a verificação do GitHub desta pesquisa

A verificação direta de metadados públicos do GitHub havia localizado:
- Uma publicação não oficial AICP 12.1 com ZIP de nome `aicp_gtexswifi_n-12.1-UNOFFICIAL-20261013.zip`, junto a uma árvore de produto que declara SM-T280. Isso prova que a publicação e a configuração de produto existem no GitHub; não prova que o ZIP seja uma compilação funcional, segura ou validada por terceiros.
- Uma árvore de dispositivo com branch `lineage-16` que declara `TARGET_OTA_ASSERT_DEVICE := SM-T280,gtexswifi`. Isso prova a presença de código de desenvolvimento associado ao nome do dispositivo; não prova a existência de uma ROM compilada, inicializável ou funcional.

Portanto, a conclusão prudente é: **LineageOS 14.1 é a candidata com relatos de uso e uma build específica apontada pela pesquisa comunitária fornecida; AICP 12.1 e as branches LineageOS mais novas permanecem pistas não validadas.** A afirmação “não existe árvore de código posterior” não deve ser usada, pois foram encontradas branches de desenvolvimento. O que ainda não foi comprovado é uma versão posterior instalável e funcional no SM-T280.

## 11. Aviso de segurança sobre FRP e instalação de complementos

O levantamento fornecido menciona contornar o FRP por edição de `build.prop` ou ferramentas de terceiros. **Essas sugestões não são aprovadas nem devem ser seguidas.** FRP é uma proteção antirroubo do Android. Não editar propriedades do sistema nem utilizar ferramentas para contornar esse bloqueio. Em caso de bloqueio, usar a recuperação oficial da conta Google anteriormente vinculada ou suporte autorizado da Samsung.

A menção a OpenGApps ARM / Android 7.1 / Pico também não constitui recomendação de instalação automática. A compatibilidade de arquitetura, versão Android, espaço de partição, pacote, recuperação e procedência deve ser verificada para a build concreta; qualquer complemento adicional aumenta o risco e consome armazenamento. Não instalar GApps ou outros ZIPs antes da auditoria do sistema-base.

## 12. Decisão de trabalho atualizada

1. **Candidata principal para auditoria:** LineageOS 14.1 Unofficial build `lineage-14.1-20210209-UNOFFICIAL-gtexswifi.zip`, indicada pela pesquisa compartilhada do Gemini.
2. **Candidata secundária apenas para inspeção:** AICP 12.1 Unofficial de 13/10/2026. Não classificar como funcional até auditar o ZIP e obter relatos independentes para SM-T280.
3. **Pistas de desenvolvimento:** trees LineageOS 15.1/16.0/17.1; não tratar seus nomes de branch como prova de ROM pronta.
4. **Antes de instalação:** localizar relatos específicos, conferir arquivo e hash, inspecionar instalador e assert de dispositivo, validar recuperação e firmware original de retorno, e confirmar backup completo. Não alterar o tablet nesta fase.

**Estado final:** LineageOS 14.1 é a primeira candidata para investigação detalhada, mas ainda não está formalmente aprovada para instalação. A prioridade continua sendo preservar o funcionamento do SM-T280 e evitar qualquer procedimento de contorno de proteção antirroubo.


## 13. Plano de pré-recuperação e preparação antes de qualquer instalação (informações fornecidas em 09/11/2026)

O Gemini propôs um checklist de preparação que foi compartilhado nesta conversa. Esta seção registra essas sugestões e acrescenta ressalvas técnicas para evitar que pré-requisitos presumidos sejam tratados como garantias.

### 13.1 Firmware original Samsung e caminho de restauração

Antes de considerar qualquer ROM customizada, será necessário:

- Identificar a região/CSC real do firmware instalado e a variante exata **SM-T280**. ZTO é apenas uma hipótese para firmware brasileiro; não selecionar CSC por suposição, pois o aparelho pode ter origem/região diferente.
- Localizar o firmware stock oficial ou uma fonte de distribuição confiável para SM-T280 e confirmar que o pacote corresponde ao modelo, CSC/região e revisão de bootloader adequados.
- Confirmar que o pacote contém os componentes necessários para a restauração e que o procedimento de retorno é documentado para este modelo.
- Validar a versão do Odin compatível com o pacote e aparelho. “Odin 3.12 ou superior” não é regra universal: a versão concreta precisa ser confirmada para o firmware e o dispositivo.
- Ter os drivers USB Samsung apropriados em um computador Windows compatível, caso o método de restauração escolhido dependa de Odin.
- Preparar cópia dos dados pessoais antes de qualquer desbloqueio ou wipe. Não considerar que uma restauração stock preserve os dados.

**Limitação do ambiente atual:** a pessoa usuária utiliza um Chromebook. Odin é uma ferramenta para Windows, e o ambiente Linux do ChromeOS não equivale a um Windows com os drivers USB Samsung. Não presumir que Odin funcione diretamente no Chromebook, por Wine, ou dentro do contêiner Linux. Se Odin for indispensável, será necessário um computador Windows compatível e com drivers adequados; não improvisar métodos de gravação alternativos.

O modo Download pode ser avaliado apenas como reconhecimento/checagem de comunicação, sem iniciar gravação. O objetivo é confirmar que o computador e o cabo reconhecem o aparelho antes de se depender desse caminho de recuperação. Não executar comandos de flash nem selecionar arquivos para gravação nesta etapa.

### 13.2 Contas Google, FRP e OEM Unlock

O plano sugerido inclui remover as contas Google do próprio tablet enquanto o Android original ainda inicia normalmente e verificar se existe a opção **Desbloqueio de OEM** nas Opções do desenvolvedor.

Ressalvas obrigatórias:

- Remover as contas Google antes de uma redefinição pode ajudar a evitar o acionamento do Google Factory Reset Protection (FRP), mas não deve ser descrito como garantia absoluta de desbloqueio.
- Manter as credenciais da conta Google anteriormente vinculada e confirmar que a pessoa proprietária consegue autenticar-se nela.
- A opção OEM Unlock pode não estar presente em todas as versões/regiões de firmware. Sua presença, estado e efeito precisam ser confirmados no SM-T280 específico.
- Ativar OEM Unlock e remover contas não substituem a verificação do estado do bootloader nem garantem que o aparelho aceitará uma imagem customizada.
- **FRP do Google, bloqueio de binário/bootloader Samsung e bloqueios de integridade são mecanismos distintos.** Um não deve ser confundido com o outro.
- Não editar `build.prop`, não executar ferramentas de bypass, não utilizar FRP Destroyer ou scripts de terceiros e não tentar contornar proteções antirroubo.
- Não redefinir o tablet apenas para testar se FRP foi removido.

Qualquer mudança no estado de OEM Unlock deverá ser tratada como uma ação posterior e deliberada, somente depois de confirmar a ROM, a recuperação, o firmware stock e o plano de retorno. Não executar agora.

### 13.3 Integridade da build LineageOS 14.1 de 09/02/2021

Arquivo candidato informado pela pesquisa comunitária:

`lineage-14.1-20210209-UNOFFICIAL-gtexswifi.zip`

Verificações necessárias, sem assumir resultados antecipadamente:

1. Abrir a página exata do arquivo no AndroidFileHost e confirmar nome, desenvolvedor, data, modelo e descrição.
2. Verificar se o desenvolvedor ou a página de download publica MD5 e/ou SHA-256. Registrar o valor informado sem o substituir por hash de outro arquivo.
3. Ao obter o arquivo, calcular localmente SHA-256 e comparar com o valor publicado. Hash calculado sem referência confiável apenas identifica o arquivo; não autentica a origem.
4. Verificar assinatura do pacote, quando disponível, e inspecionar o conteúdo do ZIP e o script de instalação para confirmar o assert de dispositivo, os destinos de partição e os componentes incluídos.
5. Conferir a versão exata do TWRP recomendada pelo desenvolvedor para **gtexswifi/SM-T280**, bem como a origem e o hash da imagem/arquivo de recuperação.
6. Não misturar recuperação, kernel, firmware, GApps ou outros ZIPs de variantes/modelos diferentes.

A página geral de arquivos informada é https://androidfilehost.com/?w=files&flid=165161. Ela precisa ser filtrada até a build exata; não basta confirmar que a pasta contém algum arquivo chamado LineageOS.

### 13.4 Estado do checklist

| Preparação | Estado |
|---|---|
| Build LineageOS 14.1 identificada pelo nome | Informada pela pesquisa da pessoa usuária; falta conferir a página e o arquivo exatos |
| Hash MD5/SHA-256 da build | Pendente |
| Assinatura e conteúdo do ZIP | Pendente |
| Versão TWRP exata para SM-T280 | Pendente |
| Firmware stock SM-T280 e CSC correto | Pendente |
| Método de restauração validado | Pendente |
| Odin e drivers em computador Windows compatível | Pendente; Chromebook não deve ser presumido compatível |
| Acesso à conta Google anteriormente vinculada | Deve ser confirmado pela pessoa proprietária antes de qualquer wipe |
| Disponibilidade e efeito de OEM Unlock | Pendente de confirmação no firmware original |
| Backup completo e verificável | Pendente |
| Teste de gravação/instalação | **Não realizado e não autorizado nesta etapa** |

**Decisão:** a LineageOS 14.1 (build de 09/02/2021) continua sendo a primeira candidata para auditoria, mas nenhuma operação de desbloqueio, wipe ou flash deve ser iniciada até que todos os itens críticos de recuperação estejam comprovados. A regra é preservar a possibilidade de retornar ao firmware original e manter as funções essenciais do SM-T280.


## 14. Proveniência das informações e colaboração com Gemini (09/11/2026)

A pessoa usuária esclareceu que as mensagens e levantamentos detalhados sobre ROMs, relatos de usuários, FRP e checklist técnico compartilhados nesta conversa são respostas do **Gemini**, utilizado em paralelo para pesquisa e análise.

Para manter uma trilha de auditoria clara, as próximas atualizações deverão distinguir:

- **Gemini — pesquisa externa relatada:** informações, links, conclusões ou recomendações apresentados pelo Gemini, ainda que detalhados. Devem permanecer atribuídos a ele até serem confirmados por uma fonte primária.
- **ChatGPT — verificação independente:** metadados, branches, arquivos, commits e releases efetivamente consultados nos repositórios pelo conector GitHub. A verificação tem escopo limitado ao conteúdo que foi realmente acessado.
- **Confirmado por fonte primária:** conteúdo verificado diretamente na publicação, arquivo, checksum, documentação do desenvolvedor ou relato identificável do usuário do SM-T280.
- **Pendente / não comprovado:** alegações sem evidência rastreável, downloads não inspecionados, builds sem teste no hardware ou documentação contraditória.

A indicação de uma informação pelo Gemini não significa que ela esteja errada; significa apenas que sua origem deve ficar clara e que ela ainda precisa de confirmação independente. Do mesmo modo, encontrar uma árvore de código ou um pacote no GitHub não prova estabilidade em hardware.

**Regra de colaboração:** usar o Gemini como segunda fonte de pesquisa e revisão, confrontar seus resultados com os repositórios e fontes primárias, registrar divergências e não elevar uma ROM a “aprovada” até que os critérios de compatibilidade e recuperação sejam comprovados.


## 15. Auditoria complementar compartilhada pelo Gemini: build, firmware stock e Chromebook (09/11/2026)

A pessoa usuária compartilhou uma nova resposta do Gemini com dados mais específicos sobre a LineageOS 14.1, firmware ZTO, TWRP, Odin, Heimdall e desempenho. **Os valores desta seção que não possuem uma fonte primária acessada diretamente permanecem atribuídos ao Gemini e não devem ser considerados validados pelo projeto.**

### 15.1 Dados da build LineageOS 14.1 informados pelo Gemini

| Campo | Valor relatado | Estado nesta auditoria |
|---|---|---|
| Nome | `lineage-14.1-20210209-UNOFFICIAL-gtexswifi.zip` | Build apontada pelo Gemini; falta conferir arquivo exato no AFH |
| Data | 09/02/2021 | Informada pelo Gemini; post original #7 do XDA ainda não foi acessado diretamente nesta sessão |
| Tamanho | 277 MB | Informado pelo Gemini; falta comparar com a página do arquivo |
| MD5 | `165611c7a063833b66c57501be11abe3` | Informado como oficial pelo Gemini; não calculado nem comparado localmente |
| Changelog | Suporte nativo a Adoptable Storage | Informado pelo Gemini; falta confirmar na mensagem do desenvolvedor |
| Recuperação | TWRP 3.4.0-3 adaptado por `_mone`; também TWRP 3.2.1-1 | Informado pelo Gemini; falta confirmar o link, arquivo e compatibilidade exatos |
| Arquivo TWRP citado | `twrp-3.4.0-3-_mone-gtexswifi.tar` | Informado pelo Gemini; não baixado nem inspecionado |

Referências comunitárias indicadas:
- AndroidFileHost: https://androidfilehost.com/?w=files&flid=165161
- Tópico XDA: https://forum.xda-developers.com/t/rom-lineageos-14-1-samsung-galaxy-tab-a-7-0-sm-t280-gtexswifi.4158061/

**Próxima verificação:** comparar nome, tamanho, MD5 e data diretamente na página do arquivo; conferir a mensagem #7 e as instruções do autor sobre TWRP. O MD5 só deve ser aceito se corresponder ao arquivo exato baixado e ao valor publicado por uma fonte primária confiável. Calcular SHA-256 local adicionalmente seria útil, mas não substitui a comparação com uma referência publicada.

### 15.2 Relatos XDA indicados pelo Gemini

O Gemini apresentou os seguintes relatos:
- `sch00n3r`, publicação de 08/12/2020, sobre instalação e problemas relacionados a FRP.
- `Mariadif`, publicação de 04/01/2021, sobre instalação usando TWRP 3.2.1-1, Odin 3.10.7 e Magisk 20.4.

Esses relatos ainda não foram abertos e confrontados diretamente nesta auditoria. A data e o conteúdo exato das mensagens precisam ser conferidos. O relato de uma instalação funcional em janeiro de 2021 não comprova automaticamente a estabilidade da build de fevereiro de 2021.

### 15.3 GApps e espaço de partição

O Gemini relata que OpenGApps ARM 7.1 Pico é o pacote adequado e que variantes maiores podem exceder o espaço disponível em `/system`.

Ressalva: **GApps não é requisito para o Android/LineageOS inicializar**; é um complemento opcional para quem deseja os serviços Google. Para este tablet, devido aos 8 GB internos e à partição de sistema limitada, a recomendação conservadora é não adicionar GApps sem necessidade e sem verificar a capacidade real, o pacote exato e a documentação da build. Não presumir que Nano/Micro sempre falhem sem conferir a mensagem e a configuração específica. O pacote deve corresponder à arquitetura e versão Android da ROM, mas nenhuma instalação de GApps está autorizada nesta etapa.

### 15.4 Firmware stock brasileiro ZTO informado pelo Gemini

O Gemini indicou:
- Modelo: SM-T280.
- Android: 5.1.1.
- PDA/build: `T280XXU0AQJ1`.
- CSC: `T280ZTO0AQJ1`.
- MD5: `7635e4c5450d5c3fdffbadad6cf34c61`.
- Revisão de bootloader: Bit 0.
- Fonte sugerida: SamFW.

**Estado:** esses valores ainda não foram confirmados diretamente em uma página de download primária, nem comparados com o CSC real do tablet. ZTO deve ser tratado como uma hipótese de região Brasil, não como CSC correto até que a região/origem e o firmware atual do aparelho sejam identificados. Não baixar nem usar firmware de outra variante ou região por semelhança do nome. O MD5 relatado pelo Gemini não foi calculado ou validado nesta sessão.

O procedimento de restauração também depende da combinação exata entre firmware, revisão de bootloader, pacote de partições e ferramenta de gravação. Não declarar que o pacote é um “arquivo único” ou que pode ser aplicado com Odin sem conferir a página e os arquivos reais.

### 15.5 Heimdall e Chromebook — verificação independente e ressalvas

Foi consultado diretamente o repositório oficial do Heimdall:
- Projeto: https://github.com/Benjamin-Dobell/Heimdall
- README: https://github.com/Benjamin-Dobell/Heimdall/blob/master/README.md
- Instruções Linux: https://github.com/Benjamin-Dobell/Heimdall/blob/master/Linux/README

O README oficial informa que:
- Heimdall é uma ferramenta open-source e multiplataforma que se comunica com dispositivos Samsung pelo protocolo USB conhecido como Odin 3, usando libusb.
- As plataformas oficialmente suportadas incluem computadores Linux x86 e x86-64, macOS e Windows; o README menciona relatos de terceiros em ARM, sem transformar isso em suporte oficial universal.
- O manual de Linux ensina a trabalhar com pacotes de firmware Heimdall ou arquivos de firmware extraídos.
- No fluxo de flash personalizado, é necessário selecionar um arquivo PIT válido e associar arquivos às partições correspondentes.
- A opção de reparticionar pode apagar os dados. O próprio manual alerta que a gravação é perigosa e pode inutilizar o dispositivo.

**Correção à sugestão recebida:** não se deve afirmar que instalar Heimdall no Crostini permite gravar diretamente um pacote Odin `.tar`/ `.tar.md5` ou uma imagem arbitrária sem preparação. O manual descreve extração, PIT e seleção de partições, e não comprova compatibilidade com o firmware específico do SM-T280. O suporte genérico a Linux tampouco comprova que o passthrough USB do ChromeOS reconhecerá o tablet em Download Mode.

**Estado para o Chromebook:** Heimdall é uma alternativa de código aberto que merece estudo porque o ambiente Linux do Chromebook pode ser x86-64, mas arquitetura, acesso USB pelo Crostini, pacote e protocolo precisam ser verificados em separado. Não executar comandos de gravação. Uma eventual detecção USB ou leitura de PIT não constitui prova de restauração completa.

### 15.6 FRP, contas Google e OEM Unlock — correção de interpretação

O Gemini sugeriu remover as contas Google do tablet original antes de qualquer wipe e conferir a opção OEM Unlock nas Opções do desenvolvedor.

A precaução de remover legitimamente as contas Google antes de uma redefinição é razoável, mas a explicação “isso evita bloqueio da partição de boot pelo FRP” é imprecisa. FRP é principalmente uma proteção antirroubo/validação de conta após uma redefinição não autorizada; bloqueios de binário personalizado e estado do bootloader Samsung são mecanismos relacionados, mas distintos.

A remoção de contas não garante que todo bloqueio seja removido, nem substitui a confirmação do estado do dispositivo. OEM Unlock pode variar com modelo e firmware/região; sua presença no menu e o comportamento real no SM-T280 devem ser confirmados antes de qualquer ação. Não alterar configurações nem realizar wipe nesta fase. Não usar ferramentas ou scripts de bypass.

### 15.7 Desempenho e multitarefa — alegações ainda sem medição

O Gemini estimou 450–600 MB de RAM em standby e cerca de 900 MB livres para aplicativos. Essa faixa **não foi medida no SM-T280 com a build específica**, e “RAM livre” não é um valor fixo: o Android usa memória para cache e serviços. Não usar essa estimativa para garantir que o tablet sustente duas ou três janelas.

Android 7.1 tem suporte de plataforma a múltiplas janelas e contempla o modo freeform em configurações compatíveis, mas isso não significa que a LineageOS específica exponha ou implemente janelas flutuantes reais por padrão. É necessário verificar overlays, recursos do framework, configuração do WindowManager, permissões e comportamento dos aplicativos. Split-screen não equivale a janelas sobrepostas. A integração do Galaxy Legacy deve começar como launcher e só avançar para janelas reais após teste em uma ROM validada.

### 15.8 Decisão de trabalho após a segunda auditoria

- **LineageOS 14.1 build 09/02/2021:** segue como primeira candidata à auditoria, apoiada por dados específicos de arquivo e relatos apontados pelo Gemini; hash, página de download, mensagens e TWRP ainda precisam de conferência independente.
- **AICP 12.1:** segue como publicação existente, porém sem evidência suficiente de estabilidade em hardware real.
- **LineageOS 15.1/16.0/17.1:** árvores de código foram encontradas; não há ZIP funcional comprovado nesta investigação.
- **Firmware stock ZTO:** build e MD5 informados pelo Gemini são pistas de pesquisa, não arquivos aprovados.
- **Heimdall no Chromebook:** opção tecnicamente plausível em Linux, mas o suporte específico ao T280, passthrough USB e formato de firmware ainda precisam ser demonstrados.
- **FRP/OEM:** não presumir desbloqueio garantido; nenhuma ferramenta de contorno será utilizada.
- **Galaxy Legacy:** começar pelo launcher e integração de APIs Android comuns. Freeform/multijanela fica como fase posterior e depende da ROM e de testes reais.

**Nenhuma ROM, recuperação ou firmware stock está aprovado para gravação.** Não houve download nem inspeção dos pacotes binários, cálculo de hash local, reconhecimento USB do SM-T280 ou teste físico.
