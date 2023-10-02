# Componente Vue.js PandaPlayer

O componente Vue.js PandaPlayer é uma integração simples para incorporar um reprodutor de vídeo da Panda Video em seu aplicativo Vue.js. Ele fornece uma maneira fácil de incorporar e controlar vídeos da Panda Video em seu aplicativo Vue.js.

## Propriedades

O componente PandaPlayer aceita várias propriedades para personalizar e controlar o reprodutor de vídeo. Aqui estão as propriedades disponíveis:

- `src` (String): A URL do vídeo que você deseja reproduzir na Panda Video.

- `queryParams` (Object): Um objeto contendo parâmetros de consulta opcionais a serem passados para o reprodutor de vídeo da Panda Video.

  <table>
  <thead>
    <tr>
      <th>Param</th>
      <th>Type</th>
      <th>Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>color</td>
      <td>String</td>
      <td>#4874F1</td>
      <td>The primary color of the player</td>
    </tr>
    <tr>
      <td>controlsColor</td>
      <td>String</td>
      <td>#FFF</td>
      <td>The color of controls and menus</td>
    </tr>
    <tr>
      <td>title</td>
      <td>String</td>
      <td>-</td>
      <td>Video title</td>
    </tr>
    <tr>
      <td>controls</td>
      <td>String</td>
      <td>play-large,play,progress,current-time,volume,captions,settings,pip,cast,fullscreen</td>
      <td>A list of enabled controls</td>
    </tr>
    <tr>
      <td>thumbnail</td>
      <td>String</td>
      <td>auto generated</td>
      <td>Thumbnail URL</td>
    </tr>
    <tr>
      <td>pauseThumbnail</td>
      <td>String</td>
      <td>generated on the frame it was paused on</td>
      <td>Thumbnail URL (pause)</td>
    </tr>
    <tr>
      <td>endThumbnail</td>
      <td>String</td>
      <td>last frame of video</td>
      <td>Thumbnail URL (end)</td>
    </tr>
    <tr>
      <td>watermark</td>
      <td>String</td>
      <td>-</td>
      <td>The watermark that appears on the video</td>
    </tr>
    <tr>
      <td>drm_group_id</td>
      <td>String</td>
      <td>-</td>
      <td>Force use a watermark group</td>
    </tr>
    <tr>
      <td>mutedIndicatorTextTop</td>
      <td>String</td>
      <td>-</td>
      <td>Muted indicator text that appears at the top</td>
    </tr>
    <tr>
      <td>mutedIndicatorTextBottom</td>
      <td>String</td>
      <td>-</td>
      <td>Muted indicator text that appears at the bottom</td>
    </tr>
    <tr>
      <td>saveProgressTitle</td>
      <td>String</td>
      <td>'Você já começou a assistir esse vídeo'</td>
      <td>Title of the save progress page</td>
    </tr>
    <tr>
      <td>saveProgressButton1Title</td>
      <td>String</td>
      <td>'Continuar assistindo'</td>
      <td>Title of the first button on the save progress page</td>
    </tr>
    <tr>
      <td>saveProgressButton2Title</td>
      <td>String</td>
      <td>'Voltar ao início'</td>
      <td>Title of the second button on the save progress page</td>
    </tr>
  </tbody>
</table>

```javascript
const playerOptions = {
  color: "#FF5733",
  controlsColor: "#000",
  title: "Meu Vídeo",
  controls: "play,progress,volume,fullscreen",
  thumbnail: "https://example.com/thumbnail.jpg",
  pauseThumbnail: "https://example.com/pause-thumbnail.jpg",
  endThumbnail: "https://example.com/end-thumbnail.jpg",
  watermark: "https://example.com/watermark.png",
  drm_group_id: "example-drm-group",
  mutedIndicatorTextTop: "Mudo",
  mutedIndicatorTextBottom: "Volume está desativado",
  saveProgressTitle: "Continue assistindo",
  saveProgressButton1Title: "Continuar",
  saveProgressButton2Title: "Recomeçar",
};
```


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
