# Winlator Fork A06 Low End

Fork experimental do Winlator para celulares Android modestos, começando pelo Galaxy A06 4G (Helio G85, 4 GB de RAM).

## Status atual

A release de teste mais recente é [v0.2.1-a06-driver-fix](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.1-a06-driver-fix). Ela inclui uma correção na preparação dos drivers gráficos para investigar a tela preta no teste Direct3D (cubo).

O APK compilou com sucesso no GitHub Actions. A correção ainda precisa ser confirmada no Galaxy A06; por enquanto, não há resultado novo do teste no aparelho.

A release anterior, [v0.2.0-a06-packs](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.0-a06-packs), continua disponível.

## O que a fork inclui

- Resolução padrão de 960x544 e cache de shaders limitado a 256 MB.
- Preparação do ambiente A06 com Vortek, Gladio, Box64, DXVK, D8VK e VKD3D.
- Componentes WinComponents selecionáveis por container.
- Packs opcionais VN/2D e 3D leve.
- Interface em português do Brasil e crédito da fork na tela Sobre.
- Preparação ordenada dos arquivos de drivers gráficos do rootfs, com atualização de versão para refazer arquivos antigos.

Compatibilidade depende do jogo ou programa, das dependências, do caminho gráfico e do driver ativo no aparelho. Os packs são pontos de partida, não garantias.

## Como testar a v0.2.1

1. Baixe o APK em [Releases](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases).
2. Faça backup dos containers antes de instalar uma build de teste.
3. No Galaxy A06 4G, abra o container e repita o teste Direct3D (cubo) com as mesmas configurações usadas antes.
4. Registre o driver gráfico, o pack ativo e se o cubo renderiza.
5. Se o teste passar, experimente primeiro uma visual novel ou jogo 2D; depois, um jogo 3D leve.

## Builds

O workflow [Build debug APK](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/actions/workflows/build-debug.yml) compila a base upstream com o patch A06 e salva o APK como artefato do Actions. Commits de release com o marcador configurado no workflow também publicam APK e notas em Releases.

## Base e créditos

A fork usa o [Winlator upstream](https://github.com/brunodev85/winlator-app) e componentes de terceiros. Os créditos desses projetos continuam válidos e aparecem no aplicativo.

As modificações específicas da fork são mantidas por **Mauricio.dev / mauricio-gamedev**. Consulte [COPYRIGHT.md](COPYRIGHT.md) para a atribuição completa.

## Limites

Esta é uma build experimental. O Galaxy A06 4G é o aparelho-alvo atual; suporte a outros celulares e compatibilidade universal não foram confirmados.
