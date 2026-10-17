# Fork do Winlator otimizada para o Galaxy A06 4G

O objetivo é criar uma versão Android leve para executar programas Windows, visual novels, point-and-click, jogos 2D/pixel art e alguns jogos 3D leves no Galaxy A06 4G, com Helio G85 e 4 GB de RAM.

## Release atual

A primeira release experimental com packs de compatibilidade está disponível em [v0.2.0-a06-packs](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.0-a06-packs).

## O que já foi implementado

- Padrão de 960x544 para reduzir carga de renderização.
- Cache de shaders limitado a 256 MB.
- Preparação automática do ambiente A06.
- Drivers Vortek e Gladio, Box64 0.4.4, DXVK 1.10.3, D8VK 1.0 e VKD3D 2.14.1 pré-carregados a partir dos assets existentes.
- Packs opcionais instaláveis por container:
  - VN/2D: DirectShow, Visual C++ 2005 e preset Box64 conservador.
  - 3D leve: DXVK, cache de shaders e preset Box64 de desempenho.
- Interface de seleção dos packs em português do Brasil.
- Copyright e crédito da fork para Mauricio.dev / mauricio-gamedev.

## Próxima etapa

Testar pelo menos uma visual novel/point-and-click e um jogo 3D leve no A06. Para cada teste, registrar a versão do jogo, pack selecionado, resolução, FPS aproximado, áudio, gráficos e travamentos.

## Build sem PC

O workflow em `.github/workflows/build-debug.yml` instala Java, Android SDK, CMake e NDK e publica o APK debug como artefato. A base upstream é baixada durante o workflow e o patch da fork é aplicado antes da compilação.

## Limites

- Compatibilidade varia entre programas e jogos.
- Um preset pode priorizar estabilidade ou velocidade; não existe uma configuração universal.
- Componentes centrais só devem ser alterados depois de medir no aparelho-alvo.

## Base de código

O código-fonte é obtido do repositório público [brunodev85/winlator-app](https://github.com/brunodev85/winlator-app). O trabalho da fork está na branch `a06-low-end-fork` e no patch em `patches/a06-low-end.patch`.
