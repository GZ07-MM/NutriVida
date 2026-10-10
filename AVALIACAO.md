# NutriVida — entrega para avaliação do curso

Entrega preparada em 10 de outubro de 2026: código web 2.4.20 e APK offline 2.4.3.1.

O APK recebeu o ícone adaptativo atualizado e preserva o frontend offline 2.4.3. As melhorias recentes do chat, ditado e cores pertencem à edição web 2.4.20 e não foram incorporadas ao APK.

## Como usar no Android

1. Baixe `NutriVida-avaliacao-v2.4.3.1.apk` no celular e abra o arquivo.
2. Se o Android solicitar, permita a instalação pelo aplicativo que abriu o arquivo e conclua a instalação.
3. Abra o NutriVida, toque em **Começar minha jornada** e preencha o cadastro local.
4. Os dados ficam neste aparelho. Não é necessário e-mail nem conexão para usar esta edição.

O APK requer Android 8 ou superior e um Android System WebView atualizado. A instalação e o comportamento no aparelho do aluno ainda precisam ser conferidos. Não houve teste em dispositivo físico nem conferência visual em navegador nesta execução.

## Roteiro para o professor

| Etapa | Ação | Resultado esperado |
|---|---|---|
| Cadastro | Preencher os seis passos | Perfil criado; joias e XP começam em zero |
| Água | Registrar um copo | Mais 200 ml no dia e nos relatórios; dez copos encerram a rotina padrão |
| Alimentação | Definir quatro horários e registrar uma refeição | Registro único por refeição; alteração de horário após o registro vale para o próximo dia |
| Preferências | Marcar alergias e alimentos a evitar | Sugestões filtradas, com ingredientes visíveis |
| Metas | Criar uma meta e registrar o que realizou | Avanço até a conclusão e registro nos relatórios |
| Sono | Informar os horários reais | Período salvo uma única vez no dia |
| Treinos | Configurar exercícios e concluir séries | O treino só é registrado ao finalizar |
| Missões | Concluir a condição e resgatar | Joias e XP entregues uma única vez |
| Continuidade | Fechar e abrir novamente o aplicativo | Registros e personalização preservados |
| Privacidade | Perfil → Privacidade e segurança → Exportar | Arquivo JSON salvo pelo seletor de arquivos do Android |
| Exclusão | Digitar EXCLUIR e confirmar | Dados deste acesso removidos |

## O que esta entrega oferece

- Modo claro branco e laranja; modo escuro futurístico roxo e laranja. Painel de sequência e navegação flutuante. O tema escolhido em Perfil → Aparência é preservado.
- Regras compartilhadas com a versão web para cadastro, metas, missões, loja, sono e treino.
- Registros offline e fonte incluída no aplicativo; nenhum serviço externo é necessário para a edição Android.
- Respostas guiadas sobre hábitos e funções do aplicativo.
- Exportação e restauração de dados, correção de registros, exclusão local e consulta de relatos de problemas.
- Abertura do despertador do celular e exportação de lembretes para o calendário.

## Limites para apresentar com clareza

A edição Android é uma entrega acadêmica instalável, com assinatura de avaliação. Não foi publicada na Play Store. Os dados Android não são sincronizados automaticamente com a conta web. É possível transferir uma cópia JSON entre versões, em Perfil → Privacidade e segurança → Restaurar uma cópia. Desinstalar o app apaga os dados locais; exporte antes de desinstalar.

As respostas da assistente são guiadas. IA generativa e pagamentos não estão conectados. O Premium está marcado como proposta e não faz cobranças. Alarmes internos exigem o aplicativo aberto; o botão do despertador abre o Relógio do celular para o usuário confirmar o alarme. Arquivos de calendário precisam ser importados e seus alertas conferidos.

A rotina padrão de água de 2.000 ml pode ser configurada pelo usuário; não é uma prescrição individual. O tamanho e a meta do dia são preservados após o primeiro registro. As ideias de alimentação e os exercícios são gerais. O aplicativo não diagnostica, prescreve tratamentos nem define restrição calórica pelo peso.

Esta entrega não constitui aprovação do professor ou de órgão público. O professor deverá avaliar os critérios do curso. Não foi informada uma rubrica ou um procedimento específico de avaliação governamental.

## Verificação técnica

As revisões do projeto incluem verificações automatizadas de domínio, cadastro direto, API local, persistência offline, campo de mensagem, ditado e movimento do teclado. O build web da versão atual foi validado. No APK, foram verificados assinatura, alinhamento, manifest e recursos adaptativos; os arquivos de código e assets do APK anterior foram preservados byte a byte. A preparação desta entrega conferiu a integridade dos ZIPs e a igualdade de cada arquivo do código com o commit de origem. Essas verificações não substituem o teste de instalação e uso em um aparelho real.

O código completo está incluído no pacote. Consulte `README.md` para a estrutura e os comandos de desenvolvimento. A chave de assinatura não integra o pacote de código.

## Revisão funcional da versão 2.4.0

- Emojis adquiridos na loja aparecem no lugar do ícone junto ao título do perfil. Meu perfil permite escolher ou remover o emoji sem perder o item comprado.
- Relatórios e calendário da sequência permitem consultar anos anteriores com as mesmas setas de mês.
- A exportação web inclui os relatos de problemas salvos neste acesso e as conversas da Nutri IA.
- Cores, estilos e ordem da navegação foram preservados.

## Funções concluídas na versão 2.4.0

- Restauração validada de backups web e offline, inclusive cópias antigas. Exige confirmação RESTAURAR e não altera senha nem reativa cronômetros.
- Correção pelos Relatórios: sono e kcal podem ser editados; água, refeições e treinos podem ser excluídos individualmente. Os totais e missões acompanham a mudança. Resgates anteriores continuam marcados para impedir recompensas duplicadas.
- Sequência conta dias com a rotina de água e quatro refeições, mais sono ou treino. A presença isolada não completa o dia.
- Missões permitem selecionar uma data e consultar qualquer período registrado.
- Rotina de água configurável, com tamanho dos copos e meta preservados no histórico.
- Consulta dos próprios relatos em Ajuda e suporte e traduções dos novos controles em inglês e espanhol.
- Seletor de arquivos do Android para restaurar o JSON.

IA online, reconhecimento por foto, pagamentos e atendimento continuam dependendo de conexões e operação externa. Perfis públicos, fotos Premium, notificações nativas em segundo plano e adaptações específicas de exercício ainda não estão implementados. O dicionário de idiomas pode deixar textos dinâmicos em português. Essas limitações não foram apresentadas como funções disponíveis.

## Saída da conta (2.4.3)

Perfil → Sair da conta está como última opção, abaixo de Premium. Na web, invalida a sessão atual; na edição offline, volta à entrada preservando todos os dados e mantém esse estado ao reabrir o app. Entrar novamente no APK retoma o perfil local, sem senha. Sair é diferente de Excluir minha conta.

## Data de nascimento (2.4.3)

Cadastro e edição de dados pessoais usam digitação numérica no formato DD/MM/AAAA. As barras aparecem após dia e mês; todo o campo recebe o toque e abre o teclado. É possível colar a data, corrigir os números e apagar sem ficar preso nas barras. Validação de datas reais, idade e armazenamento ISO foram preservados.

## Cadastro web (2.4.5)

E-mail e senha são obrigatórios; o cadastro cria a conta e inicia a sessão diretamente, sem link de confirmação nem serviço de envio de e-mail. As senhas permanecem protegidas, contas existentes não são sobrescritas e acessos de outras pessoas são isolados. O endereço informado não é verificado. O acesso do site continua privado e vinculado ao mesmo acesso do ChatGPT.

## Atualizações web incluídas até 2.4.20

- Treino pode ser escrito pelo usuário e salvo na conta.
- Aparência escolhida é restaurada ao reabrir; contas mantêm registros separados.
- A Nutri IA mantém o chat e o movimento do teclado da base aprovada 2.4.14. A revisão de respostas 2.4.15 foi revertida em 2.4.16.
- Microfone transforma fala em texto editável, sem envio automático; exige suporte e permissão do navegador.
- O toque no microfone usa animação, sem fundo azul de seleção.
- Ícones: Nutri IA azul, Sono roxo, Início laranja, Relatórios verde-água e Perfil preto no tema claro. O cabeçalho da Nutri IA também é azul.
- As respostas continuam guiadas; IA generativa e pagamentos não estão conectados.

## Ícone do APK 2.4.3.1

O desenho original foi preservado e ajustado à área segura dos ícones adaptativos do Android. Pacote `br.com.nutrivida.avaliacao`, versão `2.4.3.1-avaliacao`, código 30. Mantida a assinatura original de avaliação, sem mudança de permissões ou dos dados do aplicativo.
