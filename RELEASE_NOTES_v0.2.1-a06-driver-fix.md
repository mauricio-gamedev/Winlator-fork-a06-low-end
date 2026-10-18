## Correção de inicialização gráfica para o Galaxy A06

Esta build atualiza a preparação dos arquivos gráficos compartilhados do rootfs para evitar extrações concorrentes durante a inicialização do container. A versão do ambiente/cache A06 também foi avançada para forçar a atualização dos arquivos já instalados.

A mudança foi feita para investigar a tela preta no teste Direct3D (cubo) relatada no Galaxy A06 4G. A compilação do APK passou no GitHub Actions. Ainda falta confirmar no aparelho se o cubo voltou a renderizar.

### Como validar

1. Abra o mesmo container em que o cubo apresentou tela preta.
2. Repita o teste Direct3D com as mesmas configurações.
3. Anote o driver gráfico ativo, o pack selecionado e se o cubo renderiza.

O APK é uma build debug experimental. Faça backup dos containers antes de atualizar.
