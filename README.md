# NutriVida — site e APK 2.4.24

Código e APK da mesma versão. Esta entrega substitui os arquivos 2.4.22 na árvore principal e preserva o histórico do repositório.

- [Baixar o APK atualizado](NutriVida-v2.4.24.apk)
- [Código completo do site e do Android](NutriVida-codigo-v2.4.24.zip)
- [Roteiro de instalação e avaliação](AVALIACAO.md)
- [Ponto de retomada do desenvolvimento](RETOMADA.md)
- [Abrir o site](https://nutrivida-app.gaivotavoadora123.chatgpt.site)

## Alterações

A Nutri IA mostra um indicador de carregamento e revela o texto progressivamente. Conversas guiadas mantêm contexto para exemplos, substituições e mudanças de kcal, respeitando preferências e exclusões. O modo guiado tem uma base limitada; ainda não há um modelo generativo conectado. A resposta completa é salva antes da animação.

Os horários Dormir/Acordar e os campos do registro manual de Sono usam fonte responsiva, segmentos e ícone dentro dos cartões. Em tela muito estreita ou com texto ampliado, os campos aparecem em uma coluna. As correções anteriores de teclado e retomada do chat foram mantidas.

## Instalar e baixar

Abra o arquivo APK e use o botão de download na página do GitHub. Instale por cima do NutriVida existente, sem desinstalar. Pacote `br.com.nutrivida.avaliacao`, versão `2.4.24`, código `34` e assinatura original mantidos.

O APK funciona offline e salva contas e progresso no aparelho. Site e APK não sincronizam automaticamente: use exportação e restauração de backup no Perfil. A chave privada de assinatura e outros segredos não integram esta entrega.

## Verificação

TypeScript, builds web e Android, assinatura e alinhamento do APK passaram. O frontend do APK foi comparado byte a byte com a compilação atual. A versão 2.4.23 passou pelas verificações de contexto, animação, API local, funcionamento offline, contas, ditado e retomada; a 2.4.24 mantém essas mudanças e ajusta os campos de Sono. Instalação e inspeção visual em celular físico ainda precisam ser realizadas.

Código de origem: `7a5bf10e12130645c445b84fe8d375d74c55397c`. O ZIP contém essa base e documentos de entrega atualizados. O site mantém acesso privado.
