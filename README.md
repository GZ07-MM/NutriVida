# NutriVida — site e APK 2.4.22

Esta entrega substitui os arquivos da edição anterior por um APK completo e o código atual, ambos na versão **2.4.22**. O APK inclui as telas atuais do site, as correções do chat e teclado, treino personalizado, cores dos ícones e o ícone adaptativo. O design aprovado foi preservado.

- [Baixar o APK atualizado](NutriVida-v2.4.22.apk)
- [Código completo da mesma versão](NutriVida-codigo-v2.4.22.zip)
- [Roteiro de instalação e avaliação](AVALIACAO.md)
- [Abrir o site atualizado](https://nutrivida-app.gaivotavoadora123.chatgpt.site)

Instale o APK por cima do NutriVida existente, sem desinstalar: pacote e assinatura original foram mantidos. Na primeira criação de conta local, seu perfil e progresso antigos são vinculados ao e-mail e senha escolhidos. As próximas contas começam vazias. Não é necessário verificar e-mail.

O APK salva contas e progresso no aparelho. Não há sincronização automática com o site; use Exportar/Restaurar em Privacidade e segurança para transferir uma cópia. O ditado usa o serviço de voz do Android e solicita acesso ao microfone na primeira utilização.

A assinatura e o frontend atual do APK foram conferidos; os testes de domínio, chat, ditado, contas e API passaram. Instalação e comportamento em dispositivo físico ainda precisam ser conferidos. Toda nova entrega deve atualizar site e APK juntos.

Código de origem: `0be495ef40fe0a8e538273ddf543ffb8acfd091e`. A chave de assinatura e os segredos não estão no pacote.

## Chat ao reabrir — correção 2.4.22

A Nutri IA descarta a geometria anterior do teclado ao sair, bloquear ou voltar ao aplicativo, recalcula o campo e a navegação e ignora medidas zero no segundo plano. O rascunho e as mensagens são preservados. No Android, a retomada e o retorno do foco da janela sinalizam a atualização do layout. O CSS do design é idêntico ao APK anterior. Testes de regressão e compilação passaram; falta conferência em celular físico.

Para continuar depois, consulte [RETOMADA.md](RETOMADA.md).
