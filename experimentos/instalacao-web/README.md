# Experimento de instalação — Chrome 43

Este diretório contém uma página de teste isolada para verificar se o Chrome 43 do Galaxy Tab A SM-T280 adiciona o Galaxy Legacy à tela inicial e o abre em modo independente.

## Conteúdo
- `index.html`: página de teste e indicador do modo de abertura.
- `manifest.json`: nome, ícones, URL inicial e `display: standalone`.
- `icons/`: ícones PNG de 192 e 512 pixels.

## Restrições intencionais
- Exige hospedagem HTTPS.
- Não inclui Service Worker, Cache API ou estratégia offline.
- Não instala APK nem modifica Android.
- Não lê histórico do Chrome nem atalhos do launcher.
- Não representa ainda o protótipo visual v0.8; é somente um teste isolado.

## Procedimento de validação
1. Publicar este diretório em HTTPS, preservando os caminhos relativos.
2. Abrir a URL no Chrome 43 do SM-T280.
3. Menu do Chrome > Adicionar à tela inicial.
4. Abrir o ícone criado e observar se a barra do Chrome desaparece.
5. Registrar o resultado real, inclusive se o Chrome criar somente um atalho comum.

Não declarar compatibilidade confirmada até realizar o teste físico.
