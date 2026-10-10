# NutriVida — ponto de retomada

Salvo em 10 de outubro de 2026. Última entrega funcional: **site e APK 2.4.22**.

## Onde está o projeto

- Repositório privado: https://github.com/GZ07-MM/NutriVida/tree/main
- Site: https://nutrivida-app.gaivotavoadora123.chatgpt.site
- Código completo: `NutriVida-codigo-v2.4.22.zip`. Extraia a pasta `nutrivida/` para abrir o projeto. O repositório contém os pacotes de entrega; os arquivos de desenvolvimento estão dentro desse ZIP.
- Aplicativo instalável: `NutriVida-v2.4.22.apk`.
- Orientações de demonstração: `AVALIACAO.md`.
- Fonte que gerou a entrega: commit `0be495ef40fe0a8e538273ddf543ffb8acfd091e` do repositório de origem do Sites. A identificação do site está em `.openai/hosting.json` no checkout do Sites; esse diretório interno não integra o ZIP exportado.

O ZIP de código permite editar e reconstruir o app. O APK é o resultado compilado e não substitui o código. A chave original está na cópia privada **NutriVida-assinatura-original.zip**, guardada separadamente pelo proprietário. Ela é necessária para assinar atualizações instaláveis sobre o APK existente; não publicar a chave neste repositório ou no site.

## Preferências que devem ser mantidas

1. Atualizar **site e APK juntos** em toda alteração funcional do aplicativo. O proprietário prefere APK, e uma atualização só do site não atende à entrega.
2. Preservar o design aprovado. Não redesenhar telas ou restaurar o design antigo ao reabrir.
3. Preservar conta e progresso. No Android, manter pacote, origem do WebView e assinatura. Não desinstalar para aplicar a atualização.
4. Cadastro com e-mail e senha, sem confirmação de e-mail e sem acesso como visitante.
5. Sair da conta deve continuar como última opção do Perfil.
6. Data de nascimento digitada DD/MM/AAAA, com barras automáticas e toque em todo o campo.
7. Treino deve permitir escrever o nome desejado.
8. Nutri IA com rolagem própria, campo acompanhando o teclado, sem sobreposição com a navegação e sem seleção azul ao tocar. Ditado escreve no rascunho e não envia sozinho.
9. Ícones inferiores: Nutri IA azul, Sono roxo, Início laranja, Relatórios verde-água, Perfil preto no claro e adaptado no escuro. Ícone superior da Nutri IA azul. Manter ícone adaptativo do launcher.

## O que foi concluído

O APK foi reconstruído integralmente com as telas e estilos atuais. Foram incluídos login local, progresso isolado por conta, migração do perfil antigo para a primeira conta criada e reconhecimento nativo de voz. Contas seguintes começam sem progresso. O site foi publicado com sucesso. O GitHub recebeu código, APK e documentos 2.4.22; os pacotes antigos 2.4.20 e 2.4.3.1 foram removidos da entrega atual, preservando o histórico Git.

O script `android/build-apk.sh` exige a mesma versão no Manifest e no `package.json`, sempre recompila frontend e código nativo e rejeita o reaproveitamento de um APK antigo.

## Verificação e pendências

Passaram TypeScript, builds web/Android, 146 verificações da API local, regras de domínio, persistência offline, migração e isolamento de contas, chat/teclado e ditado. O APK passou em alinhamento e assinaturas v2/v3; seu frontend foi comparado byte a byte com o build atual.

**Ainda falta conferir em celular físico:** instalação sobre a edição anterior, vínculo do progresso à primeira conta, abertura/fechamento do teclado, ditado com permissão aceita/recusada, reabertura, exportação/restauração e alternância de contas. Não tratar testes automatizados como prova de funcionamento em todos os aparelhos.

Site e APK não sincronizam automaticamente contas ou progresso: o site usa armazenamento no servidor, vinculado à identidade do ChatGPT; o APK usa contas locais. Há transferência manual via backup JSON. A chave de assinatura não contém os dados pessoais nem o progresso do usuário. Esses dados devem ser exportados pelo próprio aplicativo antes de desinstalar ou trocar de aparelho.

A assistente disponível oferece respostas guiadas. IA generativa, pagamentos, reconhecimento de alimentos por foto e notificações nativas em segundo plano não estão conectados. Não há recuperação de senha por e-mail no APK. O ditado depende do serviço de voz do aparelho, que pode precisar de conexão. Não foi obtida aprovação do professor ou de órgão público nesta execução.

## Para a próxima sessão

Leia este arquivo, `README.md` e `AVALIACAO.md`, extraia o ZIP atual e confira os arquivos presentes no repositório antes de editar. Se houver uma versão posterior, use-a como base. Não usar uma edição antiga apenas porque ela aparece no histórico.

Para atualizar o site já existente, reutilize o projeto do Sites da conta do proprietário. Não criar outro site por engano. Para APK, aumentar `versionCode`, usar a mesma `versionName` do site e compilar com a chave privada original. O pacote atual é `br.com.nutrivida.avaliacao`, `versionCode` 32, `versionName` 2.4.22; origem local `https://app.nutrivida.local/`.

Certificado SHA-256 original: `51e8134325fced8a0d589d6d72db881240d1b697924daad04b754de9b5f6d4ad`.
APK SHA-256 da entrega atual: `285234e77c9a4a353abe27f5f4b96bd4b45fb1df6c6957fdd41117611a74dc53`.

Mensagem sugerida ao retomar: “Continue o NutriVida a partir do RETOMADA.md deste repositório. Preserve o design e meu progresso, e entregue site e APK atualizados juntos.”

## Última correção — retorno à Nutri IA

Em 2.4.22, foram corrigidas medidas de teclado e deslocamento mantidas ao sair, bloquear ou voltar ao app. O controlador observa pausa/retomada, pageshow, visibilidade e foco; limpa dados transitórios, evita medidas zero e refaz a medição do campo e da navegação. A Activity Android sinaliza a retomada e o retorno do foco da janela. A permissão de ditado conserva a sessão de teclado; a saída real preserva o rascunho e encerra o foco anterior.

Testes novos simulam pausa com teclado aberto, pan antigo, rotação em segundo plano, cold start, retomada com medidas atrasadas, permissão de microfone e limpeza dos listeners. TypeScript e os builds web/Android passaram; o CSS do APK foi conferido como idêntico ao 2.4.21. A instalação e a reprodução no aparelho físico continuam pendentes.
