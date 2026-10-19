# Pinky Paws 🎀🐱 — React Native + Expo Go

Aplicativo mobile de lembretes em **React Native, JavaScript e Expo**, inspirado no protótipo do Stitch. Os prints originais estão em `assets/reference/` para consulta. Não é um projeto Vite nem React Web.

## 1. Preparar o computador

Instale Node.js LTS, VS Code e o app **Expo Go** no celular. Descompacte esta pasta e abra-a no VS Code.

## 2. Instalar e executar

No terminal, dentro da pasta `pinky-paws-expo`:

```bash
npm install
npx expo install --fix
npx expo start
```

Abra o Expo Go no celular e escaneie o QR Code do terminal. Celular e computador devem estar na mesma rede Wi-Fi. Se a conexão falhar, experimente `npx expo start --tunnel` (pode solicitar instalar `@expo/ngrok`).

> O Expo SDK 54 é usado aqui. `npx expo install --fix` alinha versões nativas compatíveis com a instalação do SDK.

## 3. Funcionalidades

- Criar, listar, buscar, editar, concluir e excluir lembretes
- Nome, descrição, data, horário e recorrência (nenhuma, diária, semanal, mensal e personalizada por dia da semana)
- Tela de aviso com concluir, adiar 5/10/30 minutos e cancelar notificações
- Configuração geral de notificações
- Armazenamento persistente local via AsyncStorage
- Notificações locais com expo-notifications (permissão do aparelho necessária)

**Limitação importante:** para recorrências, esta versão agenda apenas a **próxima ocorrência**. Depois que ela dispara, a próxima repetição não é reagendada automaticamente com o aplicativo fechado; editar ou salvar o lembrete agenda a próxima. Para notificações recorrentes indefinidamente em segundo plano, será necessário melhorar o agendador. O botão do sino no topo permite simular o aviso. As notificações podem ter restrições no Expo Go, dependendo do dispositivo e versão do Expo SDK; testes em build de desenvolvimento são mais confiáveis.

**Campos de data e hora:** por simplicidade, usam entrada no formato `AAAA-MM-DD` e `HH:MM`, com validação.

## 4. GitHub

Crie um repositório vazio no GitHub e execute:

```bash
git init
git add .
git commit -m "Criar aplicativo Pinky Paws com Expo"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/pinky-paws.git
git push -u origin main
```

Substitua `SEU-USUARIO`. A pasta `node_modules` é ignorada automaticamente pelo `.gitignore`.

## 5. Organização

- `App.js`: telas, estilos, dados e lógica do aplicativo
- `index.js`: entrada do React Native
- `app.json`: configuração do Expo
- `package.json`: dependências e scripts
- `assets/reference`: telas de referência do Stitch
