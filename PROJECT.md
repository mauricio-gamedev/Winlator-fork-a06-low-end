# Fork do Winlator otimizada para o Galaxy A06 4G

O objetivo é criar uma versão Android leve para executar programas Windows, visual novels, point-and-click, jogos 2D/pixel art e alguns jogos 3D leves no Galaxy A06 4G, com Helio G85 e 4 GB de RAM.

## Release de teste atual

A [v0.2.2-a06-pack-fix](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.2-a06-pack-fix) revisa a instalação dos packs de compatibilidade após o teste A/B no A06 mostrar tela preta no cubo somente com pack ativo.

## O que mudou nos packs

- Versão interna dos packs avançada para v2. Containers com pack v1 mostram **atualização disponível**.
- Instalar o pack grava as opções no container e invalida o cache dos componentes para reaplicação na próxima inicialização.
- O pack não extrai DLLs diretamente; a instalação passa pelo fluxo normal do Winlator, incluindo os ajustes de DLLs e registro na ordem esperada.
- O pack 3D leve preserva o driver gráfico, wrapper Direct3D, preset Box64 e variáveis personalizadas já escolhidos.
- A tela inicial do container informa quando um pack antigo precisa ser atualizado.

A alteração mira o conflito entre a extração direta feita durante a instalação do pack e o fluxo normal de preparação do Wine. A build precisa ser testada novamente no Galaxy A06 para confirmar se o cubo voltou a renderizar.

## Funcionalidades da fork

- Padrão de 960x544 para reduzir carga de renderização.
- Cache de shaders limitado a 256 MB.
- Preparação automática do ambiente A06, com atualização versionada do rootfs e do cache dos drivers gráficos.
- Drivers Vortek e Gladio, Box64 0.4.4, DXVK 1.10.3, D8VK 1.0 e VKD3D 2.14.1 pré-carregados a partir dos assets existentes.
- Packs opcionais instaláveis por container:
  - VN/2D: DirectShow, Visual C++ 2005 e dependências de áudio/vídeo.
  - 3D leve: Direct3D e Visual C++ 2010, preservando o caminho gráfico atual.
- Interface de seleção dos packs em português do Brasil.
- Copyright e crédito da fork para Mauricio.dev / mauricio-gamedev.

## Próximos testes

1. Atualizar um container com pack v1 e repetir o teste Direct3D (cubo) no A06 com o pack v2.
2. Comparar o resultado com um container sem pack usando o mesmo driver e wrapper.
3. Se o cubo renderizar nos dois, testar uma visual novel ou point-and-click e depois um jogo 3D leve.

Registre a versão do app, pack, driver, wrapper, resolução, FPS aproximado, áudio, gráficos e travamentos. Compatibilidade gráfica ainda está em validação.

## Build sem PC

O workflow em `.github/workflows/build-debug.yml` instala Java, Android SDK, CMake e NDK, baixa a base upstream e aplica o patch da fork. Cada build debug é salvo como artefato do Actions; commits de release marcados conforme o workflow publicam APK e notas.

## Limites

- Compatibilidade varia entre programas e jogos.
- Um preset pode priorizar estabilidade ou velocidade; não existe uma configuração universal.
- Componentes centrais só devem ser alterados depois de medir no aparelho-alvo.
- O Galaxy A06 4G é o primeiro alvo; suporte a outros aparelhos ainda não foi estabelecido.

## Base de código

O código-fonte é obtido do repositório público [brunodev85/winlator-app](https://github.com/brunodev85/winlator-app). O trabalho da fork está na branch `a06-low-end-fork` e no patch em `patches/a06-low-end.patch`.
