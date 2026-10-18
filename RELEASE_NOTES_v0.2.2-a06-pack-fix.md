## Packs de compatibilidade v2

Esta versão corrige a preparação do container ao instalar um pack. A versão anterior extraía componentes Windows diretamente durante a instalação do pack. A v2 deixa a extração de DLLs e os ajustes do Wine para a inicialização normal do container e invalida os caches para que esse fluxo reaplique os arquivos na ordem padrão.

O pack 3D leve não força mais DXVK, Box64 em desempenho ou variáveis de threading/sincronização. Ele preserva o driver gráfico, o wrapper Direct3D, o preset Box64 e as variáveis personalizadas já configuradas.

### Atualizar um container existente

Containers com o pack v1 mostram **atualização disponível**. Reinstale o pack v2 pela tela de packs e inicie o container uma vez para aplicar as mudanças. A tela preta foi reproduzida pelo usuário com o pack e não ocorreu no container sem pack; ainda é necessário confirmar o resultado após esta correção no Galaxy A06.

Esta é uma build debug experimental. Faça backup dos containers antes de atualizar.
