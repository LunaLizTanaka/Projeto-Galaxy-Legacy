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
