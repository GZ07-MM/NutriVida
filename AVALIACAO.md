# NutriVida — entrega para avaliação do curso

Versão 2.3.1, preparada em 7 de outubro de 2026.

## Como usar no Android

1. Baixe `NutriVida-avaliacao.apk` no celular e abra o arquivo.
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
- Exportação de dados, exclusão local e relatos de problemas disponíveis na exportação.
- Abertura do despertador do celular e exportação de lembretes para o calendário.

## Limites para apresentar com clareza

A edição Android é uma entrega acadêmica instalável, com assinatura de avaliação. Não foi publicada na Play Store. Os dados Android não são sincronizados com a conta da versão web. Desinstalar o app apaga os dados locais; exporte antes de desinstalar.

As respostas da assistente são guiadas. IA generativa e pagamentos não estão conectados. O Premium está marcado como proposta e não faz cobranças. Alarmes internos exigem o aplicativo aberto; o botão do despertador abre o Relógio do celular para o usuário confirmar o alarme. Arquivos de calendário precisam ser importados e seus alertas conferidos.

A rotina de água de 2.000 ml é um padrão de acompanhamento do aplicativo, não uma prescrição individual. As ideias de alimentação e os exercícios são gerais. O aplicativo não diagnostica, prescreve tratamentos nem define restrição calórica pelo peso.

Esta entrega não constitui aprovação do professor ou de órgão público. O professor deverá avaliar os critérios do curso. Não foi informada uma rubrica ou um procedimento específico de avaliação governamental.

## Verificação técnica

Foram executados testes de regras de domínio, 25 verificações de confirmação de e-mail, 105 operações da API local e 52 operações offline. A compilação TypeScript, o build web, o build do frontend Android e a assinatura do APK foram verificados. Os testes são automatizados e não substituem o teste de instalação, navegação e exportação em um aparelho real.

O código completo está incluído no pacote. Consulte `README.md` para a estrutura e os comandos de desenvolvimento. A chave de assinatura não integra o pacote de código.
