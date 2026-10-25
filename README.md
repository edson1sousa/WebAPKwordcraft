# WordCraft Web APK (Android WebView)

Este projeto é um invólucro Android simples que abre o editor web WordCraft Online dentro de um aplicativo.

- URL carregada: `https://wordcraft.run/editor`
- Nome do app: WordCraft Web
- ID Android: `app.wordcraft.web`
- Requer internet para carregar o editor.
- Inclui seletor de arquivos para tentar abrir documentos no editor e suporte básico a downloads.

## Importante

`wordcraft.run` é um site independente que hospeda uma versão comunitária do WordCraft, não o site oficial do projeto original. Consulte a página About e os termos do site antes de usar. O WordCraft está em fase alpha e o editor web pode ter limitações no celular.

A compatibilidade de salvar/exportar arquivos dentro de WebView precisa ser testada no aparelho. Alguns navegadores tratam downloads gerados por JavaScript/blob de forma diferente; por isso, não considere o APK pronto para documentos importantes sem testar primeiro.

## Gerar o APK com GitHub Actions (sem Android Studio local)

1. Crie um repositório no GitHub e envie estes arquivos para a branch `main`.
2. Abra a aba **Actions** do repositório.
3. Se solicitado, habilite GitHub Actions.
4. Execute **Build WordCraft Web APK** com **Run workflow**, ou envie um commit para `main`.
5. Quando terminar, abra a execução e baixe o artefato `WordCraftWeb-debug-apk`.
6. Extraia o ZIP baixado; o arquivo será `app-debug.apk`.
7. Transfira o APK para o Android e instale. Talvez seja necessário permitir a instalação de apps dessa fonte nas configurações do Android.

## Gerar pelo Android Studio

1. Abra esta pasta no Android Studio.
2. Use JDK 17 e Gradle 8.9.
3. Aguarde a sincronização e selecione **Build > Build APK(s)**.
4. O APK de teste fica em `app/build/outputs/apk/debug/app-debug.apk`.

## Personalizar

- Para mudar o endereço carregado, altere `editorUrl` em `MainActivity.kt`.
- Para mudar o nome, altere `app_name` no manifesto (o nome atual é `WordCraft Web`).
- Para publicar na Play Store, será necessário criar uma versão release assinada e revisar as políticas de conteúdo e privacidade.

## Fontes

- WordCraft original: https://github.com/storytold/wordcraft
- WordCraft Online (hospedagem independente): https://wordcraft.run/about
- Android WebView: https://developer.android.com/develop/ui/views/layout/webapps/webview
