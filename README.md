Componente Vue.js PandaPlayer
O componente Vue.js PandaPlayer é uma integração simples para incorporar um reprodutor de vídeo da Panda Video em seu aplicativo Vue.js. Ele fornece uma maneira fácil de incorporar e controlar vídeos da Panda Video em seu aplicativo Vue.js.

Instalação
Para começar a usar o componente Vue.js PandaPlayer, siga estas etapas:

Instale o componente Vue.js PandaPlayer usando o npm ou yarn:

bash
Copy code
npm install vue-panda-player
# ou
yarn add vue-panda-player
Importe o componente em seu arquivo Vue:

javascript
Copy code
import PandaPlayer from 'vue-panda-player';

export default {
  components: {
    PandaPlayer,
  },
  // ...
}
Use o componente em seu template Vue:

html
Copy code
<template>
  <PandaPlayer :src="videoSrc" :queryParams="videoQueryParams" />
</template>
Configure as propriedades conforme necessário. Consulte a seção a seguir para obter informações sobre as propriedades disponíveis.

Propriedades
O componente PandaPlayer aceita várias propriedades para personalizar e controlar o reprodutor de vídeo. Aqui estão as propriedades disponíveis:

src (String): A URL do vídeo que você deseja reproduzir na Panda Video.

queryParams (Object): Um objeto contendo parâmetros de consulta opcionais a serem passados para o reprodutor de vídeo da Panda Video. Por exemplo, você pode definir opções de legendas, qualidade de vídeo, etc.

fullscreen (Boolean): Indica se o vídeo deve ser exibido em tela cheia ou não.

getCurrentTime (Function): Uma função de retorno de chamada para obter o tempo atual do vídeo.

onTimeUpdate (Function): Uma função de retorno de chamada para lidar com eventos de atualização de tempo do vídeo.

onProgress (Function): Uma função de retorno de chamada para lidar com eventos de progresso do vídeo.

onReady (Function): Uma função de retorno de chamada para lidar com o evento de vídeo pronto para reprodução.

onPlay (Function): Uma função de retorno de chamada para lidar com eventos de reprodução do vídeo.

onPause (Function): Uma função de retorno de chamada para lidar com eventos de pausa do vídeo.

onSeeking (Function): Uma função de retorno de chamada para lidar com eventos de busca no vídeo.

onSeeked (Function): Uma função de retorno de chamada para lidar com eventos de busca concluída no vídeo.

onEnded (Function): Uma função de retorno de chamada para lidar com eventos de finalização do vídeo.

onEnterFullscreen (Function): Uma função de retorno de chamada para lidar com eventos de entrada em tela cheia do vídeo.

onExitFullscreen (Function): Uma função de retorno de chamada para lidar com eventos de saída da tela cheia do vídeo.

onCaptionsEnabled (Function): Uma função de retorno de chamada para lidar com eventos de ativação de legendas no vídeo.

onCaptionsDisabled (Function): Uma função de retorno de chamada para lidar com eventos de desativação de legendas no vídeo.

onLanguageChange (Function): Uma função de retorno de chamada para lidar com eventos de alteração de idioma no vídeo.

onCanPlay (Function): Uma função de retorno de chamada para lidar com eventos de disponibilidade de reprodução do vídeo.

onError (Function): Uma função de retorno de chamada para lidar com eventos de erro do vídeo.

onSpeedUpdate (Function): Uma função de retorno de chamada para lidar com eventos de atualização de velocidade do vídeo.
