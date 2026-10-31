# Buddy OS Lite — relógio e pet digital

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

## Instalar no celular

1. Publique todos os arquivos desta pasta em um site HTTPS estático, por exemplo GitHub Pages ou Netlify.
2. Abra o endereço no Chrome do Android.
3. No menu do Chrome, escolha **Instalar app** ou **Adicionar à tela inicial**.
4. Abra o Buddy pelo ícone instalado.
5. Toque uma vez na tela para permitir o modo de tela ativa, se o navegador oferecer suporte.

O PWA precisa estar hospedado em HTTPS para que a instalação e o cache offline funcionem corretamente.

## Personalizar a cidade do clima

No arquivo `index.html`, procure por `latitude=-23.55&longitude=-46.63` e troque pelas coordenadas da cidade desejada. As coordenadas atuais são de São Paulo.

## Dica para usar como relógio de cabeceira

Mantenha o celular conectado ao carregador, reduza o brilho e desative o bloqueio automático de tela enquanto estiver usando o Buddy. A tela permanentemente ligada pode aquecer o aparelho e desgastar a bateria; verifique a temperatura ocasionalmente.
