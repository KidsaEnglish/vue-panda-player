# Componente Vue.js PandaPlayer

O componente Vue.js PandaPlayer é uma integração simples para incorporar um reprodutor de vídeo da Panda Video em seu aplicativo Vue.js. Ele fornece uma maneira fácil de incorporar e controlar vídeos da Panda Video em seu aplicativo Vue.js.

## Propriedades

O componente PandaPlayer aceita várias propriedades para personalizar e controlar o reprodutor de vídeo. Aqui estão as propriedades disponíveis:

- `src` (String): A URL do vídeo que você deseja reproduzir na Panda Video.

- `queryParams` (Object): Um objeto contendo parâmetros de consulta opcionais a serem passados para o reprodutor de vídeo da Panda Video. Por exemplo, você pode definir opções de legendas, qualidade de vídeo, etc.

- `fullscreen` (Boolean): Indica se o vídeo deve ser exibido em tela cheia ou não.

- `getCurrentTime` (Function): Uma função de retorno de chamada para obter o tempo atual do vídeo.

- `onTimeUpdate` (Function): Uma função de retorno de chamada para lidar com eventos de atualização de tempo do vídeo.

- `onProgress` (Function): Uma função de retorno de chamada para lidar com eventos de progresso do vídeo.

- `onReady` (Function): Uma função de retorno de chamada para lidar com o evento de vídeo pronto para reprodução.

- `onPlay` (Function): Uma função de retorno de chamada para lidar com eventos de reprodução do vídeo.

- `onPause` (Function): Uma função de retorno de chamada para lidar com eventos de pausa do vídeo.

- `onSeeking` (Function): Uma função de retorno de chamada para lidar com eventos de busca no vídeo.

- `onSeeked` (Function): Uma função de retorno de chamada para lidar com eventos de busca concluída no vídeo.

- `onEnded` (Function): Uma função de retorno de chamada para lidar com eventos de finalização do vídeo.

- `onEnterFullscreen` (Function): Uma função de retorno de chamada para lidar com eventos de entrada em tela cheia do vídeo.

- `onExitFullscreen` (Function): Uma função de retorno de chamada para lidar com eventos de saída da tela cheia do vídeo.

- `onCaptionsEnabled` (Function): Uma função de retorno de chamada para lidar com eventos de ativação de legendas no vídeo.

- `onCaptionsDisabled` (Function): Uma função de retorno de chamada para lidar com eventos de desativação de legendas no vídeo.

- `onLanguageChange` (Function): Uma função de retorno de chamada para lidar com eventos de alteração de idioma no vídeo.

- `onCanPlay` (Function): Uma função de retorno de chamada para lidar com eventos de disponibilidade de reprodução do vídeo.

- `onError` (Function): Uma função de retorno de chamada para lidar com eventos de erro do vídeo.

- `onSpeedUpdate` (Function): Uma função de retorno de chamada para lidar com eventos de atualização de velocidade do vídeo.

## Funções de Controle

Além das propriedades, o componente Vue.js PandaPlayer oferece funções de controle que podem ser usadas com uma referência (`ref`) do componente. Essas funções permitem que você interaja e controle o reprodutor de vídeo Panda Video incorporado em seu aplicativo Vue.js. Abaixo estão as funções de controle disponíveis:

### `getInternalPlayer()`

Esta função retorna a instância do reprodutor Panda Video incorporado. Você pode usá-la para acessar métodos e propriedades adicionais do reprodutor diretamente.

### `play()`

A função `play()` inicia a reprodução do vídeo.

### `pause()`

A função `pause()` pausa a reprodução do vídeo.

### `togglePlay()`

A função `togglePlay()` alterna entre reprodução e pausa do vídeo.

### `destroy()`

A função `destroy()` remove e destrói o reprodutor de vídeo Panda Video do DOM. Use esta função quando não precisar mais do reprodutor.

### `increaseVolume(step)`

A função `increaseVolume(step)` aumenta o volume do vídeo pelo valor especificado em `step`. Você pode passar um número positivo para aumentar o volume.

### `decreaseVolume(step)`

A função `decreaseVolume(step)` diminui o volume do vídeo pelo valor especificado em `step`. Você pode passar um número positivo para diminuir o volume.

### `toggleCaptions()`

A função `toggleCaptions()` ativa ou desativa as legendas do vídeo.

### `toggleControls(value)`

A função `toggleControls(value)` permite controlar a exibição dos controles do vídeo. Se `value` for `true`, os controles serão exibidos; se `false`, os controles serão ocultados.

### `exitFullscreen()`

A função `exitFullscreen()` sai do modo de tela cheia, se estiver ativado.

### `toggleFullscreen()`

A função `toggleFullscreen()` alterna entre o modo de tela cheia e o modo normal.

### `forward(seekTime)`

A função `forward(seekTime)` avança o vídeo por um período de tempo especificado em segundos, conforme definido em `seekTime`.

### `rewind(seekTime)`

A função `rewind(seekTime)` retrocede o vídeo por um período de tempo especificado em segundos, conforme definido em `seekTime`.

### `setCurrentTime(time)`

A função `setCurrentTime(time)` define o tempo atual de reprodução do vídeo para o valor especificado em segundos, conforme definido em `time`.

### `setVolume(volume)`

A função `setVolume(volume)` define o volume do vídeo para o valor especificado em `volume`, onde `volume` deve estar entre 0 (mudo) e 1 (volume máximo).

Essas funções de controle permitem uma integração flexível e personalizada do reprodutor Panda Video em seu aplicativo Vue.js, permitindo que você crie uma experiência de vídeo sob medida para suas necessidades específicas.
