# Proffy Mobile

Aplicativo Android (Kotlin) da disciplina Programação para Dispositivos Móveis.

## Identificação

- **Nome completo:** Roberto Filho Lima Silva
- **Turma:** Sistemas de Informação

## Fluxo "Esqueci minha senha"

A tela `ForgotPasswordActivity` (`ui/forgot`) é aberta pelo botão "Esqueci minha senha" da `LoginActivity`. A validação do e-mail usa o utilitário `EmailValidator` (`util`), que remove espaços e confere o formato com `Patterns.EMAIL_ADDRESS`; o mesmo utilitário também é usado pela `RegisterStepTwoActivity`. Um `addTextChangedListener` valida enquanto o usuário digita e alterna o botão entre o estado inicial (cinza, desabilitado, "Entrar") e o válido (verde, habilitado, "Enviar"), seguindo o padrão de `setButtonState` já usado no cadastro. Ao sair do campo com um e-mail inválido, o `TextInputLayout` exibe a mensagem de erro abaixo do campo, que some quando o e-mail fica válido. Ao tocar em "Enviar", a `ForgotPasswordActivity` cria uma `Intent` explícita para a `FinallyActivity` e envia por extras o título, o subtítulo e o texto do botão (vindos do `strings.xml`), como já faz o fluxo de cadastro. Na `FinallyActivity`, o botão "Voltar ao login" abre a `LoginActivity` com `FLAG_ACTIVITY_NEW_TASK` e `FLAG_ACTIVITY_CLEAR_TASK`, limpando a pilha de navegação.
