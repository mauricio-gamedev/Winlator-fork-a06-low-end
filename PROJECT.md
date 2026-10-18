# Fork do Winlator otimizada para o Galaxy A06 4G

O objetivo é criar uma versão Android leve para executar programas Windows, visual novels, point-and-click, jogos 2D/pixel art e alguns jogos 3D leves no Galaxy A06 4G, com Helio G85 e 4 GB de RAM.

## Release de teste atual

A [v0.2.1-a06-driver-fix](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.1-a06-driver-fix) atualiza a preparação dos arquivos gráficos compartilhados do rootfs. A alteração investiga a tela preta relatada no teste Direct3D (cubo).

O GitHub Actions compilou o APK com sucesso. A renderização do cubo nesta build ainda precisa ser verificada fisicamente no Galaxy A06 4G. A [v0.2.0-a06-packs](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.0-a06-packs) permanece disponível como release anterior.

## O que já foi implementado

- Padrão de 960x544 para reduzir carga de renderização.
- Cache de shaders limitado a 256 MB.
- Preparação automática do ambiente A06, com atualização versionada do rootfs e do cache dos drivers gráficos.
- Drivers Vortek e Gladio, Box64 0.4.4, DXVK 1.10.3, D8VK 1.0 e VKD3D 2.14.1 pré-carregados a partir dos assets existentes.
- Packs opcionais instaláveis por container:
  - VN/2D: DirectShow, Visual C++ 2005 e preset Box64 conservador.
  - 3D leve: DXVK, cache de shaders e preset Box64 de desempenho.
- Interface de seleção dos packs em português do Brasil.
- Copyright e crédito da fork para Mauricio.dev / mauricio-gamedev.

## Próximos testes

1. Repetir o teste Direct3D (cubo) no A06 com a v0.2.1 e anotar o driver e o pack ativos.
2. Se o cubo renderizar, testar uma visual novel ou jogo point-and-click.
3. Depois testar um jogo 3D leve; anotar versão do jogo, resolução, FPS aproximado, áudio, gráficos e travamentos.

O APK passou pela compilação automatizada. A compatibilidade gráfica ainda está em validação no aparelho; não assumir suporte geral antes dos testes.

## Build sem PC

O workflow em `.github/workflows/build-debug.yml` instala Java, Android SDK, CMake e NDK, baixa a base upstream e aplica o patch da fork. Cada build debug é salvo como artefato do Actions; um commit de release marcado conforme o workflow publica também um APK debug e as notas na página Releases.

## Limites

- Compatibilidade varia entre programas e jogos.
- Um preset pode priorizar estabilidade ou velocidade; não existe uma configuração universal.
- Componentes centrais só devem ser alterados depois de medir no aparelho-alvo.
- O Galaxy A06 4G é o primeiro alvo; suporte a outros aparelhos ainda não foi estabelecido.

## Base de código

O código-fonte é obtido do repositório público [brunodev85/winlator-app](https://github.com/brunodev85/winlator-app). O trabalho da fork está na branch `a06-low-end-fork` e no patch em `patches/a06-low-end.patch`.
