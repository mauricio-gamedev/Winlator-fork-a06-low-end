# Winlator Fork A06 Low End

Fork experimental do Winlator para celulares Android modestos, começando pelo Galaxy A06 4G (Helio G85, 4 GB de RAM).

## Status

A build atual é um APK debug para testes no aparelho. A primeira release experimental com os packs está disponível em [v0.2.0-a06-packs](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.0-a06-packs).

Ela já inclui:

- resolução padrão de 960x544 e cache de shaders limitado a 256 MB;
- preparação automática do ambiente A06 com Vortek, Gladio, Box64, DXVK, D8VK e VKD3D;
- componentes WinComponents selecionados por container;
- packs opcionais de compatibilidade VN/2D e 3D leve;
- interface em português do Brasil e crédito da fork na tela Sobre.

A compatibilidade ainda está sendo medida com jogos e programas reais. O pack recomendado depende do software escolhido.

## Como testar

1. Baixe o APK em [Releases](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases).
2. Crie ou abra um container e entre em **Packs de compatibilidade A06**.
3. Use o pack **VN / 2D** para visual novels, point-and-click e jogos 2D antigos.
4. Use o pack **3D leve** para jogos 3D que usam DXVK.
5. Registre o jogo, resolução, pack usado, FPS aproximado e qualquer erro de áudio ou vídeo.

## Build sem PC

O workflow [Build debug APK](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/actions/workflows/build-debug.yml) baixa a base upstream, instala Java/Android SDK/CMake/NDK, aplica o patch A06 e publica o APK como artefato. A release é publicada pelo workflow específico depois de uma compilação limpa.

## Base e créditos

A fork usa o [Winlator upstream](https://github.com/brunodev85/winlator-app) e componentes de terceiros. Os créditos desses projetos continuam válidos e aparecem no aplicativo.

As modificações específicas da fork são mantidas por **Mauricio.dev / mauricio-gamedev**. Consulte [COPYRIGHT.md](COPYRIGHT.md) para a atribuição completa.

## Limites

Esta é uma build experimental. Compatibilidade depende do programa, das dependências, do caminho gráfico e do driver disponível no aparelho. Nenhum pack garante que todos os jogos funcionarão.
