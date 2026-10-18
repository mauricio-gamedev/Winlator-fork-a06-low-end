# Winlator Fork A06 Low End

Fork experimental do Winlator para celulares Android modestos, começando pelo Galaxy A06 4G (Helio G85, 4 GB de RAM).

## Status atual

A release de teste atual é [v0.2.2-a06-pack-fix](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.2-a06-pack-fix). Ela revisa os packs de compatibilidade após o teste mostrar tela preta no cubo com pack instalado e renderização normal sem pack.

Na versão 2, instalar um pack atualiza as configurações do container e pede que a próxima inicialização reaplique os componentes pela sequência normal do Winlator. O fluxo do pack não extrai DLLs por conta própria e não troca o driver gráfico, o wrapper Direct3D ou as variáveis personalizadas do container.

A compilação automatizada será publicada junto com a release. Ainda é necessário confirmar o resultado do cubo no Galaxy A06 4G. A release anterior, [v0.2.1-a06-driver-fix](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases/tag/v0.2.1-a06-driver-fix), continua disponível.

## O que a fork inclui

- Resolução padrão de 960x544 e cache de shaders limitado a 256 MB.
- Preparação do ambiente A06 com Vortek, Gladio, Box64, DXVK, D8VK e VKD3D.
- Componentes WinComponents selecionáveis por container.
- Packs opcionais VN/2D e 3D leve.
- Packs atualizados preservam o driver e o wrapper escolhidos e deixam a instalação de DLLs para a inicialização normal do container.
- Interface em português do Brasil e crédito da fork na tela Sobre.

Compatibilidade depende do jogo ou programa, das dependências, do caminho gráfico e do driver ativo no aparelho. Os packs são pontos de partida, não garantias.

## Como testar a v0.2.2

1. Baixe o APK em [Releases](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/releases).
2. Faça backup dos containers antes de instalar uma build de teste.
3. Em um container que usava o pack v1, abra **Packs de compatibilidade A06** e instale novamente o pack marcado como **atualização disponível**.
4. Inicie o container para que o Winlator reaplique os componentes e o wrapper selecionados.
5. Repita o teste Direct3D (cubo) com o mesmo driver e wrapper; compare com um container sem pack.

Registre o pack, o driver, o wrapper e se o cubo renderiza. A confirmação precisa ser feita no aparelho.

## Builds

O workflow [Build debug APK](https://github.com/mauricio-gamedev/Winlator-fork-a06-low-end/actions/workflows/build-debug.yml) compila a base upstream com o patch A06 e salva o APK como artefato do Actions. Commits de release marcados no workflow também publicam APK e notas na página Releases.

## Base e créditos

A fork usa o [Winlator upstream](https://github.com/brunodev85/winlator-app) e componentes de terceiros. Os créditos desses projetos continuam válidos e aparecem no aplicativo.

As modificações específicas da fork são mantidas por **Mauricio.dev / mauricio-gamedev**. Consulte [COPYRIGHT.md](COPYRIGHT.md) para a atribuição completa.

## Limites

Esta é uma build experimental. O Galaxy A06 4G é o aparelho-alvo atual; suporte a outros celulares e compatibilidade universal não foram confirmados.
