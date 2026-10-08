# NutriVida

## Arquivos desta entrega

- [Código completo v2.3.1](NutriVida-codigo-v2.3.1.zip): 183 arquivos do projeto web e Android, com telas, funções, imagens, testes e documentação.
- [APK Android v2.3.1](NutriVida-avaliacao-v2.3.1.apk): aplicativo de avaliação para instalação no celular.

Para abrir o código, baixe e extraia o ZIP. A pasta `NutriVida` contém os arquivos do projeto; o roteiro do curso está em `AVALIACAO.md`. O APK é uma entrega pronta para instalar, não um instalador de ferramentas de desenvolvimento.

Esta entrega copia o código e o aplicativo. Não transfere contas, registros pessoais do banco web ou conversas do ChatGPT. Novas alterações no aplicativo precisam de uma nova entrega neste repositório.

Aplicativo de organização de hábitos: água, refeições, sono, treinos, metas, missões, patentes e personalização. Versão 2.3.1.

A entrega para o curso está documentada em [AVALIACAO.md](AVALIACAO.md), incluindo instalação, roteiro de demonstração, funcionalidades e limitações.

## Edições

- **Web:** React 19 / Vinext / Vite, Worker Cloudflare e D1, com acesso privado e contas protegidas por senha. Cadastro exige envio e confirmação de e-mail; `RESEND_API_KEY` e `EMAIL_FROM` precisam estar configurados. Não há confirmação simulada em produção.
- **Android de avaliação:** APK com uma Activity Java e WebView que carrega somente arquivos incluídos no pacote. Funciona offline; dados armazenados no aparelho, sem senha ou sincronização. Fonte, imagens e código estão incluídos. O Manifest não solicita internet, contatos, localização, câmera ou acesso amplo a arquivos. Exportação usa o seletor de documentos do Android.
- **Demonstração web:** `/demo` usa os mesmos registros locais do Android, separados da conta web e limitados ao navegador/aparelho atual.

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
| `tests/` | Verificações de domínio, e-mail, API e persistência offline |

## Desenvolvimento

Requisitos: Node 22.13 ou superior e pnpm 11.25.0. Use a versão indicada em `packageManager`.

```sh
pnpm install --frozen-lockfile
pnpm dev
pnpm build
node node_modules/typescript/bin/tsc --noEmit
pnpm test:domain
pnpm test:email
pnpm test:offline
pnpm test:api
```

O teste da API exige o build web e aplica as migrações somente no banco **local**. Ele usa uma caixa de e-mail simulada de teste para conferir a confirmação sem enviar mensagens reais. Não execute os testes da API contra produção.

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
