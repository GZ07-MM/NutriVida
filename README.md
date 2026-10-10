# NutriVida — entrega atualizada

Preparada em 10 de outubro de 2026 para atualizar o repositório privado `GZ07-MM/NutriVida`.

## Arquivos desta entrega

- [Código completo web v2.4.20](NutriVida-codigo-v2.4.20.zip): 214 arquivos do projeto, incluindo código Android, recursos, testes e documentação.
- [APK Android v2.4.3.1](NutriVida-avaliacao-v2.4.3.1.apk): edição offline com o ícone adaptativo ajustado.
- [Roteiro de avaliação](AVALIACAO.md).

O ZIP reproduz os arquivos de código rastreados do commit `8f510b0ee6376f9ded673199da9f2f8f7860bf80`, sem arquivos internos de publicação. Extraia a pasta `NutriVida` para abrir o projeto.

**As edições têm versões diferentes:** o código web está em 2.4.20; o APK mantém o frontend offline 2.4.3 e recebeu apenas a atualização do ícone, identificada como 2.4.3.1. As mudanças recentes de chat, ditado e cores do site estão no código web, não neste APK.

O site mantém o design aprovado, o chat e seu acompanhamento do teclado, o ditado por microfone, as cores dos ícones e o ícone azul no cabeçalho da Nutri IA. Cadastro web exige e-mail e senha, sem verificação por mensagem.

Contas, progresso pessoal, banco de produção, conversas do ChatGPT e chave de assinatura não fazem parte desta entrega. A publicação no GitHub não é sincronização automática do aplicativo.

O arquivo `EMAIL_SETUP.md` dentro do código registra a configuração antiga de confirmação de e-mail; esse fluxo foi desativado e não é necessário para o cadastro web atual.

## Documentação do projeto

Aplicativo de organização de hábitos: água, refeições, sono, treinos, metas, missões, patentes e personalização. Versão 2.4.20.

A entrega para o curso está documentada em [AVALIACAO.md](AVALIACAO.md), incluindo instalação, roteiro de demonstração, funcionalidades e limitações.

## Edições

- **Web:** React 19 / Vinext / Vite, Worker Cloudflare e D1, com acesso privado e contas protegidas por senha. Cadastro direto com e-mail e senha, sem confirmação por mensagem. E-mail é um identificador informado pelo usuário, não uma identidade verificada. Senhas são protegidas por PBKDF2 e a sessão fica vinculada ao acesso do ChatGPT.
- **Android de avaliação:** APK com uma Activity Java e WebView que carrega somente arquivos incluídos no pacote. Funciona offline; dados armazenados no aparelho, sem senha ou sincronização. Fonte, imagens e código estão incluídos. O Manifest não solicita internet, contatos, localização, câmera ou acesso amplo a arquivos. Exportação usa o seletor de documentos do Android.
- **Acesso web:** conta com e-mail e senha obrigatória. A opção de avaliação sem conta foi removida; `/demo` redireciona para o login. O APK de avaliação anterior continua separado e offline, sem autenticação por e-mail.

## Estrutura

| Pasta | Conteúdo |
|---|---|
| `app/` | Telas, componentes, tradução e rotas web |
| `lib/domain.ts` | Perfil, missões, níveis, loja e regras de calendário |
| `lib/state-actions.ts` | Regras compartilhadas entre API e versão offline |
| `lib/local-store.ts` | Persistência e operações offline, com fila de gravação |
| `lib/guided-chat.ts` | Orientações guiadas compartilhadas |
| `db/` e `drizzle/` | Acesso ao banco e migrações |
| `android/` | Manifest, Activity Java, recursos, entrada Vite e build do APK |
| `public/` | Imagens, fonte Inter e licença |
| `tests/` | Verificações de domínio, cadastro, API, persistência offline e chat |

## Desenvolvimento

Requisitos: Node 22.13 ou superior e pnpm 11.25.0. Use a versão indicada em `packageManager`.

```sh
pnpm install --frozen-lockfile
pnpm dev
pnpm build
node node_modules/typescript/bin/tsc --noEmit
pnpm test:domain
pnpm test:offline
pnpm test:api
```

O teste da API exige o build web e aplica as migrações somente no banco **local**. Ele confere cadastro direto, login, duplicatas e requisições simultâneas sem enviar mensagens reais. Não execute os testes da API contra produção.

## APK de avaliação

O frontend pode ser compilado com `pnpm build:android:web`. O APK usa Java 8 e ferramentas Android obtidas dos pacotes Ubuntu/Debian. O build executado nesta entrega usou JRE 17, ECJ 3.32.0, `libandroid-23-java`, `dalvik-exchange`, `aapt`, `zipalign` e `apksigner` 31.0.2. O APK tem `minSdkVersion=26` e `targetSdkVersion=28`; é destinado a instalação para avaliação, não a publicação na Play Store.

`android/build-apk.sh` reproduz a compilação com uma pasta que contenha os pacotes extraídos e uma chave de avaliação. Exemplo:

```sh
NUTRIVIDA_ANDROID_TOOLS=/caminho/android-tools NUTRIVIDA_KEYSTORE=/caminho/avaliacao.jks bash android/build-apk.sh
```

A chave deve ter senha `android`, usada exclusivamente para esta assinatura de avaliação. Ela não é incluída no código exportado. O script gera, alinha, assina e verifica `android/build/NutriVida-avaliacao.apk`. Uma chave diferente não poderá atualizar uma instalação assinada com a chave original; para preservar dados, exporte antes de reinstalar.

## Recursos não conectados

IA generativa é opcional na edição web e exige `OPENAI_API_KEY`. Sem ela, respostas guiadas continuam disponíveis. Premium está em preparação e não faz cobranças. Alarmes internos precisam do app aberto; no Android o botão de alarme abre o Relógio do aparelho para confirmação. As regras de saúde, privacidade e os limites da entrega estão descritos em `AVALIACAO.md`.

## Validação e aprovação

Os testes automatizados e a verificação de assinatura passaram. A instalação em dispositivo físico e a conferência visual em navegador não foram realizadas neste ambiente. Não existe aprovação oficial associada a este projeto. A avaliação depende dos critérios do curso e, se aplicável, do procedimento do órgão responsável.

## Dados e correções (2.4.0)

Perfil → Privacidade e segurança exporta e restaura cópias JSON. A restauração substitui o histórico deste acesso após validar o arquivo e exigir RESTAURAR; não importa credenciais nem inicia alarmes ou treinos antigos. Serve também para transferir manualmente dados entre web e APK, sem sincronização automática.

Relatórios permite corrigir sono e kcal e excluir um registro de água, refeição ou treino. Recompensas previamente resgatadas permanecem marcadas. A sequência exige a rotina diária de água, quatro refeições e sono ou treino. A tela Água permite configurar copos e volume; mudanças após registrar o primeiro copo valem no próximo dia.

A substituição de registros usa transação e revisão no servidor; gravações concorrentes não são descartadas silenciosamente. Backups antigos sem marcação de resgate conservam as missões já concluídas como resgatadas. As cópias contêm informações pessoais: guarde-as com cuidado.

Sair da conta está em Perfil, como última opção, abaixo de Premium. Na web, encerra a sessão; no Android offline, volta à entrada e mantém o perfil salvo. A saída local é preservada ao fechar e abrir o app; Continuar minha jornada permite retomar sem apagar registros.

### Treino escrito pelo usuário (web 2.4.6)

Em Treinos, escolha “Escrever meu treino”, informe um nome de 3 a 80 caracteres e configure séries, repetições e tempo. O nome fica salvo na sessão e aparece ao voltar à tela. Pausa, cronômetro, conclusão e missões seguem as mesmas regras dos exercícios prontos. O APK disponível continua na edição offline 2.4.3.

### Aparência ao reabrir (web 2.4.7)

O design atual é aplicado permanentemente, sem depender da marcação `data-design`. As preferências de aparência são restauradas no início da página, antes do login; ao entrar, as configurações salvas na conta prevalecem. O cache de aparência contém apenas tema, tamanho de texto e movimento, sem dados pessoais ou progresso. Cores, medidas, ícones e layout foram preservados. O APK já distribuído continua na versão 2.4.3.

### Teclado da Nutri IA (web 2.4.8)

O campo de mensagem acompanha teclados que cobrem a página ou reduzem sua altura. A barra inferior volta ao fechar o teclado; a ordem e o design permanecem os mesmos. Enviar por toque preserva o foco, e o texto digitado enquanto a resposta chega não é apagado. Acompanhamento usa eventos de viewport sincronizados com os frames, sem aplicar animação atrasada. APK distribuído permanece 2.4.3.

### Movimento do chat (web 2.4.9)

A pergunta aparece imediatamente ao enviar, e o campo fica livre para a próxima mensagem com o teclado aberto. O histórico acompanha respostas e movimento do teclado quando o usuário está no fim da conversa; ao subir para ler mensagens antigas, a rolagem automática pausa. Enviar uma mensagem ou voltar ao fim retoma o acompanhamento. Respostas pendentes são reconciliadas com os registros da conta sem duplicar os balões. Aparência do chat, folhas de estilo, ícones e navegação permanecem iguais.

### Tela de conversa (web 2.4.10)

A Nutri IA usa uma área de histórico com rolagem própria, cabeçalho estável e campo de mensagem que acompanha a área visível do teclado. O campo aceita múltiplas linhas, cresce até cinco linhas e deixa o texto rolar depois disso. No computador, Enter envia e Shift+Enter quebra a linha; no celular, Enter quebra a linha. O campo e o formulário desativam preenchimento automático e identificam o texto como mensagem, sem afetar o cadastro. As perguntas ficam à direita e as respostas sem balão; a tela não exibe o painel fixo de orientações guiadas. As respostas continuam usando o serviço configurado ou o modo guiado disponível. Os controles de teclado e gerenciadores de senhas pertencem ao sistema/navegador, portanto não há garantia de reprodução idêntica do teclado do ChatGPT. Conta, histórico e progresso continuam salvos. APK distribuído permanece 2.4.3.

### Aparência e limite da conversa (web 2.4.11)

Restaurados os balões, cores, saudação e cabeçalho anteriores da Nutri IA. A conversa mantém a rolagem própria e o campo de várias linhas com preenchimento de credenciais desativado. A altura real da navegação e do campo reserva o espaço da tela; o campo fica 15px acima da barra inferior, inclusive com texto grande. Enquanto o teclado está aberto, a navegação é ocultada e volta ao fechar; sua ordem não muda. Conta e progresso são preservados.

### Teclado e sobreposição observados no celular (web 2.4.12)

A regra geral `.app` impunha `min-height:100vh` à tela fixa da Nutri IA. Isso anulava a altura do viewport visível, causando sobreposição com a navegação e escondendo o campo atrás do teclado. A tela de chat passa a usar `min-height:0` e limita sua altura ao viewport medido. A correção não altera as regras das outras telas, as cores, balões ou ícones.

### Cursor de digitação (web 2.4.13)

O campo de mensagem da Nutri IA exibe somente o cursor ao receber foco, sem o contorno retangular. A aparência do restante do chat e os indicadores de foco das outras telas são preservados.

### Movimento do teclado (web 2.4.14)

O espaço entre o campo e o limite visível da conversa diminui continuamente durante a abertura do teclado. O campo não troca mais de posição de uma vez ao ultrapassar o limite de detecção. A navegação permanece oculta até o teclado terminar de fechar; eventos simultâneos de redimensionamento são agrupados e eventos repetidos não provocam novas rolagens. Os testes cobrem abertura e fechamento em etapas, inclusive após perder o foco, com teclado sobreposto e WebView que redimensiona a janela, além de navegação maior. Aparência e cursor da versão anterior são preservados.

### Respostas guiadas e identificação de assuntos (web 2.4.15)

A Nutri IA continua no modo guiado, sem chave de API criada ou conexão generativa habilitada. O reconhecimento usa palavras completas e expressões por assunto, evitando confundir dormir/despertador/computador com dor. Funções do app têm respostas próprias: perfil, conta, Premium em preparação, loja, relatórios, metas, missões, patentes, aparência, idioma, notificações, backup e jornada. Perguntas com vários assuntos recebem respostas separadas; continuação curta usa o assunto recente e pedidos ambíguos pedem esclarecimento. Isso é reconhecimento por regras, não compreensão geral de linguagem.

Os totais são lidos da conta atual, para hoje ou ontem, incluindo tamanho e alvo do copo do dia. Sugestões de refeições usam o catálogo existente e suas preferências, exclusões e restrições citadas recentemente. Instruções de treinos vêm do catálogo do app. O chat não grava hábitos, muda configurações, compra itens ou apaga dados por ordem textual. Histórico e progresso permanecem vinculados à conta; visual e movimento do chat não mudam.

Referências para orientações gerais: [Guia alimentar do Ministério da Saúde](https://bvsms.saude.gov.br/bvs/publicacoes/guia_alimentar_populacao_brasileira_2ed.pdf), [hábitos de sono do CDC](https://www.cdc.gov/sleep/about/index.html) e [SAMU 192](https://www.gov.br/saude/pt-br/composicao/saes/samu-192). A conversa não diagnostica nem prescreve dietas restritivas, medicamentos ou tratamentos.

### Restauração da versão aprovada (web 2.4.16)

Desfeita a atualização das respostas guiadas 2.4.15 após o relato de regressão no chat e na aparência. O comportamento retorna à base 2.4.14, aprovada pelo usuário antes das alterações da IA. Mantidos o cursor sem contorno, o acompanhamento contínuo do teclado e todos os arquivos visuais dessa base. Conta, histórico e progresso não foram alterados; nenhuma migração ou limpeza de dados foi executada. As melhorias de respostas permanecem recuperáveis no histórico Git, mas não estão ativas nesta versão.

### Ditado na Nutri IA (web 2.4.17)

O botão de microfone transforma a fala em texto editável na caixa de mensagem. Um segundo toque encerra o ditado; o usuário revisa e envia pelo botão de envio. Não há envio automático. O texto digitado antes de ditar é preservado, resultados parciais são atualizados sem duplicação e editar manualmente interrompe o microfone. O ditado termina ao sair da tela ou colocar o app em segundo plano. Mantidos os demais estilos e o controle do teclado da versão aprovada.

Usa `SpeechRecognition`/`webkitSpeechRecognition`, com o idioma do perfil (português, inglês ou espanhol). Requer suporte do navegador e permissão de microfone; o serviço de reconhecimento do navegador pode processar áudio remotamente e precisar de internet. Navegadores sem suporte exibem orientação para usar o microfone do teclado. O app não grava arquivos de áudio. Os testes simulam resultados parciais/finais, interrupções e erros; o microfone de um celular real não foi testado neste ambiente. Esta atualização é do site web; o APK existente não foi reconstruído.

### Animação do microfone (web 2.4.18)

O microfone mantém o fundo transparente ao ser selecionado. Removido o destaque azul de toque do navegador nesse botão. Ao pressionar, o ícone diminui suavemente e volta ao tamanho original; durante o ditado há uma pulsação discreta no ícone. O foco de teclado continua visível em roxo. As opções de movimento reduzido desativam as animações. Os demais estilos, posições do chat e comportamento do ditado foram preservados. Build validado; a animação não foi verificada visualmente em um celular neste ambiente.

### Cores dos ícones da navegação (web 2.4.19)

Os ícones mantêm sua cor própria, selecionados ou não: Nutri IA azul, Sono roxo, Início laranja, Relatórios verde-água e Perfil preto no tema claro. No tema escuro, os tons ficam mais claros para manter a visibilidade, inclusive Perfil. Mantidos os desenhos dos ícones, rótulos, estados selecionados, dimensões e a ordem Nutri IA → Sono → Início → Relatórios → Perfil. O ajuste é apenas de cores e não modifica o chat ou o ditado. Build validado; sem verificação visual em navegador/celular neste ambiente.

### Ícone do cabeçalho da Nutri IA (web 2.4.20)

Corrigida a prioridade do estilo do ícone no topo da Nutri IA: a regra compartilhada de cabeçalhos deixava o ícone roxo apesar do tom azul definido na tela. Ele agora usa o mesmo azul da navegação inferior, com adaptação aos temas claro e escuro. Mantidos o fundo, o desenho, as dimensões e todo o restante da interface. Build validado; sem verificação visual em celular neste ambiente.

### Ícone adaptativo do APK (Android 2.4.3.1)

Mantida a maçã branca com traço laranja e o fundo laranja do ícone original. O launcher agora usa um ícone adaptativo em `mipmap-anydpi-v26`, com camadas de fundo e primeiro plano de 108 dp. A marca foi centralizada e escalada a 72% dos paths anteriores, preservando o desenho dentro da zona segura circular de 66 dp para recortes redondos e arredondados. O recurso legado permanece disponível.

O APK desta entrega é uma atualização de recursos da edição offline 2.4.3: `versionCode` 30, `versionName` 2.4.3.1-avaliacao. O pacote e a chave original de avaliação foram preservados. Os 17 arquivos de assets/código do APK anterior são idênticos byte a byte; as atualizações do site web não foram incorporadas nesta edição. Não houve mudança de permissões nem migração de dados. Assinaturas v2/v3, alinhamento, manifest e recursos compilados foram verificados. As margens foram renderizadas e a zona segura validada; instalação em um aparelho real não foi testada neste ambiente.

Para reproduzir apenas a atualização do ícone, sem reconstruir o frontend, use `NUTRIVIDA_BASE_APK=/caminho/NutriVida-avaliacao.apk` junto das variáveis de ferramentas e chave descritas acima ao executar `android/build-apk.sh`. Sem essa variável, o script continua fazendo o build completo. Referência: [ícones adaptativos do Android](https://developer.android.com/develop/ui/compose/system/icon_design_adaptive).
