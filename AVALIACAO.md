# NutriVida — roteiro de avaliação

Site e APK atualizados para **2.4.21**, em 10 de outubro de 2026.

## Instalação e atualização Android

1. Baixe `NutriVida-v2.4.21.apk` e abra no celular. Se o Android solicitar, permita a instalação pelo aplicativo que abriu o arquivo.
2. Instale como atualização do NutriVida existente, sem desinstalar. O pacote e a assinatura original foram mantidos.
3. Quem usava a edição antiga deve criar a primeira conta local com e-mail e senha. O perfil e o progresso anteriores serão vinculados a essa conta. Para uma instalação nova, preencha o cadastro após criar a conta.
4. Não há confirmação por e-mail. Contas adicionais começam sem progresso; sair e entrar novamente mantém os registros de cada conta.

Requer Android 8 ou superior e Android System WebView atualizado. Dados do APK ficam neste aparelho e não são sincronizados automaticamente com o site. Exporte uma cópia antes de desinstalar. O APK não oferece recuperação de senha por e-mail.

## Demonstração

| Etapa | Ação | Resultado esperado |
|---|---|---|
| Conta | Criar conta com e-mail e senha | Acesso direto, sem mensagem de confirmação |
| Cadastro | Digitar a data DD/MM/AAAA | Barras automáticas e data válida |
| Água | Registrar um copo | Registro nos totais e relatórios |
| Alimentação | Configurar horários e registrar refeição | Registro único por refeição |
| Treino | Escrever o nome e concluir as séries | Nome personalizado e registro ao finalizar |
| Sono | Informar horários reais | Período salvo no dia |
| Missões | Cumprir a condição e resgatar | XP e joias entregues uma única vez |
| Nutri IA | Perguntar sobre água, sono, alimentação ou treino | Orientação guiada sobre o assunto e funções do app |
| Ditado | Tocar no microfone, falar e parar | Texto no rascunho, sem envio automático |
| Chat | Abrir e fechar o teclado; ler mensagens antigas | Campo na área visível e rolagem do histórico |
| Aparência | Escolher tema e reabrir | Tema e design atual preservados |
| Conta | Perfil → última opção → Sair da conta | Volta ao login sem apagar progresso |
| Isolamento | Criar outra conta e alternar acessos | A nova conta começa vazia e a anterior mantém os registros |
| Backup | Exportar e restaurar com RESTAURAR | Dados validados, sem credenciais ou alarmes reativados |
| Exclusão | Confirmar EXCLUIR | Apenas a conta atual e seus dados removidos |

## Apresentação das funções

O APK inclui as telas e estilos atuais do site, inclusive chat, treino personalizado, cores dos ícones e ícone adaptativo para o launcher. O ditado Android depende de permissão do microfone e do serviço de reconhecimento disponível no aparelho; esse serviço pode precisar de conexão e processar a fala externamente.

A assistente oferece respostas guiadas. IA generativa, pagamentos, foto para reconhecimento de alimentos e notificações nativas em segundo plano não estão conectados. Premium é uma proposta, sem cobrança. Despertadores e calendários precisam ser confirmados no aplicativo correspondente do aparelho.

As ideias de alimentação e exercícios são gerais. O NutriVida não faz diagnóstico ou prescrição. A meta de água é configurável e não representa recomendação individual de saúde.

## Verificação

Testes automatizados conferem regras de domínio, API local, operações offline, migração do perfil antigo, isolamento de contas, persistência, alterações de sessão e transcrição por voz. A compilação web/Android, a versão, o alinhamento e a assinatura do APK são verificados. Não foi realizado teste em dispositivo Android físico nesta execução.

Esta entrega não constitui aprovação do professor ou de órgão público. O professor deve aplicar os critérios do curso; não foi fornecida uma rubrica governamental específica. O código completo está no arquivo `NutriVida-codigo-v2.4.21.zip`, sem chave de assinatura ou segredos.
