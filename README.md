# Flutter - Apple Deploy

## Xcode - Bundle ID
- dentro do projeto na pasta ```ios``` - right button mouse - open Xcode
- formato: br.empresa.nomeapp
  - br - indica que o app é do Brasil
  - empresa - representa a empresa
  - nomeapp - nome do app

## [Apple Developer](developer.apple.com)
- Login
- Certificates, IDs & Profiles
  - Identifiers
    - App IDs
    - App
    - Descrição
    - Bundle ID - explicit: igual o xcode
    - continue - register
- App Store Connect
  - Apps
    - +
      - iOS
      - Nome
      - Portuguese (Brazil)
      - Seleciona o Bundle ID cadastrado
      - SKU: nomeapp-app
      - Full Access
      - Create

## Xcode
- Runner
  - Supported Destinations
    - Iphone
  - Minimium Deployments
    - iOs: 16.6
  - Identify
    - Version: 1.0.0
    - Build: 1
  - Signing & Capabities
    - [x] Automatically manage signing - cria automaticamente o perfil de visionamento
    - Team - selecionar a conta
    - [x] Device…
    - Register Device
  - Signing & Capabities - outra maneira de realizar
    - iphone conectado
    - window
      - devices and simulators
        - copiar o identifier do iphone
    - acessar o apple developer
      - Certificates, IDs & Profiles
        - Devices
          - +
            - Device Name
            - Device ID (UDID)
            - Continue
            - Register

## pubspec.yaml
- version: 1.0.0+1
- +1 número do build

## Adicionando o ícone do aplicativo
- [IconKitchen](https://icon.kitchen/i/H4sIAAAAAAAAA6tWKkvMKU0tVrKqVkpJLMoOyUjNTVWySkvMKU6t1VHKzU8pzQHJRisl5qUU5WemKOkoZeYXA8ny1CSl2FoApT8%2BHkAAAAA%3D)
- Upload do ícone
- Alterar o bg
- Download
- ios
  - Runner
    - Assets.xcassets
      - AppIcon.appiconset
        - deletar os .png
        - colar os novos
- Xcode - assets para verificar como ficou

## Gerando o arquivo (archive) de build e enviando para a loja
- Rodar o comando: ```flutter build ipa```
- App [Transporter](https://apps.apple.com/br/app/transporter/id1450874784?mt=12)
  - Login com a conta de DEV
  - Enviar o arquio IPA gerado
  - Entregar
  - Liberado no TestFlight caso envie com sucesso

## TestFlight
- Missing Compliance
  - Manage
    - [x] None of the algorithms mentioned above // caso não use criptografia avançada
    - Save
- Internal Testing
  - Para adicionar testers
  - Create New Internal Group
- Invite Testers
  - E-mail do testador
- Quem for testar precisa:
  - Instalar o app: TestFlight
  - Aguardar o e-mail com o convite

## Distribution - passo final
- Add for Review
- App Information
  - Definir os diretos de conteúdo (se você é o criador do conteúdo do app)
  - Escolher a categoria principal do app
- Age Rating
  - Informar a frequencia de conteúdos: como linguagem forte, humor adulto, conteúdo sexual, etc. Mesmo que não tenha nada disso, você precisa marcar como “nunca”.
- App Privacy
  - Colocar o link da política de privacidade
  - Preencher o questionário sobre práticas de coleta de dados
- Localização - Português (Brasil)
  - URL de suporte -> esse campo é obrigatório
  - Palavras-chave (Keywords)
  - Descrição do app
- Screenshot obrigatória de 6.5 polegadas
  - A Apple exige pelo menos uma captura de tela do app rodando em um Iphone com tela grande, como o Iphone 15 Plus ou Iphone 13 Pro Max.
- Build vinculado à versão
  - Confirme se o build que subimos já está vinculado à versão que vamos enviar.
  - Caso não esteja, selecione o build certo no campo “Build” dessa tela.
- Preço e Disponibilidade (Princing and Availability)
  - Vá até a aba de Preço, defina se o app será gratuito ou pago
  - Escolha também em quais países o app estará disponível
- Add for Review
- Submit to App Review

## Fonte
- [Publique seu App Flutter na App Store! - Guia Completo de Lançamento](https://www.youtube.com/watch?v=bMHBfdLmB2Y&ab_channel=FlutterBrasil)

