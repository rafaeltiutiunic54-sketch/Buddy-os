# Buddy OS Retro — relógio e pet digital

Esta versão foi simplificada para funcionar em um celular Android antigo, usado como relógio e pet digital de cabeceira.

## O que o Buddy faz

- Mostra hora e data em tempo real.
- Mantém os olhos, humor, animações e rede neural local do pet original.
- Exibe clima e cotação do dólar/euro.
- Busca manchetes de Tecnologia, Fórmula 1, Mundo, Economia e Brasil.
- Salva as últimas notícias, clima e cotações no armazenamento do próprio celular.
- Se a internet cair, mantém os últimos dados carregados.
- Não usa OpenAI, IA, Supabase, banco de dados externo ou chave de API.

## Como as atualizações funcionam

- Notícias: verifica se precisa atualizar a cada 5 minutos; só baixa novos feeds quando já se passaram 30 minutos.
- Clima: a cada 30 minutos.
- Dólar e euro: a cada 30 minutos.
- Ao abrir o aplicativo ou voltar para ele, verifica se há dados vencidos.

As atualizações automáticas acontecem enquanto o PWA está aberto. Um PWA comum não consegue executar atualizações periódicas confiáveis quando o Android encerra o aplicativo ou deixa o navegador suspenso. Ao abrir novamente, ele atualiza o que estiver vencido.

## Fontes utilizadas

- Notícias G1: Tecnologia, Mundo, Economia e Brasil, via RSS.
- Fórmula 1: feed RSS do Autosport.
- Conversão de RSS para JSON: serviço público RSS2JSON.
- Clima: Open-Meteo.
- Câmbio: AwesomeAPI.

Os serviços são externos e gratuitos para uso básico, mas podem sofrer instabilidade, mudar endereços ou impor limites. Se uma fonte falhar, as outras ainda podem atualizar. As últimas informações válidas permanecem salvas no aparelho.

## Instalar no celular usando GitHub Pages (gratuito)

1. Entre em https://github.com ou crie uma conta.
2. Toque em **New repository** (Novo repositório).
3. Dê um nome, por exemplo `buddy-os`, selecione **Public** e crie o repositório.
4. Dentro do repositório, escolha **Add file > Upload files**.
5. Extraia o ZIP do Buddy e envie **todos os arquivos que estão dentro da pasta**: `index.html`, `manifest.webmanifest`, `sw.js` e `buddy-icon.svg`. Não envie apenas o ZIP e não coloque os arquivos dentro de uma segunda pasta.
6. Toque em **Commit changes** para salvar os arquivos.
7. Abra **Settings > Pages** no repositório.
8. Em **Build and deployment**, selecione **Deploy from a branch**.
9. Em **Branch**, selecione `main` e a pasta `/ (root)`. Toque em **Save**.
10. Aguarde alguns minutos. O GitHub mostrará um endereço parecido com `https://SEU-USUARIO.github.io/buddy-os/`.
11. Abra esse endereço no Chrome do Android. Se aparecer o Buddy, abra o menu ⋮ do Chrome e escolha **Instalar app** ou **Adicionar à tela inicial**.
12. Abra pelo novo ícone. Não use o arquivo `index.html` baixado diretamente.

Se a opção de instalação não aparecer, atualize a página, aguarde a publicação terminar e confira se o endereço começa com `https://`.

### Atualizar uma versão já instalada

Quando enviar arquivos atualizados ao mesmo repositório, o GitHub Pages publicará a nova versão. Feche o Buddy, abra novamente com internet e atualize a página. Se ainda aparecer a versão antiga, feche o app, abra o endereço do site no Chrome e atualize novamente. O cache foi versionado para facilitar a troca da versão anterior.

O PWA precisa estar hospedado em HTTPS para que a instalação e o cache offline funcionem corretamente.

## Localização do clima

O clima está configurado para **Sorocaba - SP** (coordenadas aproximadas: latitude `-23.5015`, longitude `-47.4526`). Para mudar a cidade, altere esses valores na URL do Open-Meteo dentro do arquivo `index.html`.

## Dica para usar como relógio de cabeceira

Mantenha o celular conectado ao carregador, reduza o brilho e desative o bloqueio automático de tela enquanto estiver usando o Buddy. A tela permanentemente ligada pode aquecer o aparelho e desgastar a bateria; verifique a temperatura ocasionalmente.


## Atualização visual Retro

Esta versão mantém o pet local, o relógio, o clima, o câmbio, as notícias e a central. A interface recebeu tema de terminal retrô/CRT, olhos mais expressivos, ícones de clima, controles de modo descanso, efeitos CRT, animações e segundos do relógio nas configurações. A localização do clima está configurada para Sorocaba - SP. Ao publicar uma atualização, o service worker usa o cache `buddy-os-retro-v3`; feche e reabra o app ou recarregue a página hospedada para buscar a versão nova.

## Atualização visual e personalização

A versão atual inclui eventos espontâneos locais do mascote (sem IA), com falas e mudanças temporárias de expressão em intervalos aleatórios. Em Configurações é possível escolher temas Retro Verde, Âmbar, Azul ou Monocromático; ou escolher Personalizado e ajustar a cor principal, brilho, intensidade CRT e velocidade das animações. Também há controle para ativar/desativar os eventos espontâneos. As preferências são salvas localmente no aparelho.
