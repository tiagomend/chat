# Casos de Uso

## UC001: Enviar Mensagens de Texto em Tempo Real
- **Nome:** Enviar Mensagens de Texto em Tempo Real
- **Escopo:** Sistema de Chat
- **Nível:** Usuário
- **Ator Principal:** Usuário do Sistema

### Interessados e Interesses:
- **Usuário:** Deseja se comunicar instantaneamente com outros usuários sem interrupções.

### Pré-condições:
- O usuário deve estar autenticado e logado no sistema.
- O usuário deve ter uma conversa ativa com pelo menos um destinatário.
- O sistema deve estar operacional e conectado à Internet.

### Pós-condições:
- A mensagem enviada pelo usuário é recebida instantaneamente pelo(s) destinatário(s).
- O sistema registra a mensagem no histórico de conversas.

### Cenário de Sucesso Principal (Fluxo Básico):
1. O usuário abre a conversa com o destinatário.
2. O usuário digita uma mensagem no campo de entrada de texto.
3. O usuário clica no botão de envio ou pressiona a tecla "Enter".
4. O sistema utiliza WebSockets para enviar a mensagem ao destinatário.
5. O sistema confirma que a mensagem foi entregue e a exibe na interface do usuário.
6. O destinatário recebe a mensagem em tempo real e ela aparece na sua tela.

### Extensões (Fluxo Alternativo):
1. **Falha na Conexão de Internet:**
    - Se a conexão de Internet do usuário falhar enquanto a mensagem está sendo enviada:
        1. O sistema exibe uma mensagem de erro informando que a mensagem não pode ser enviada.
        2. O usuário pode tentar reenviar a mensagem quando a conexão for restabelecida.
2. **Erro no Servidor:**
    - Se ocorrer um erro no servidor ao tentar enviar a mensagem:
        1. O sistema exibe uma mensagem de erro ao usuário.
        2. O usuário é notificado e a mensagem não é enviada.
3. **Mensagens Proibidas:**
    - Se o usuário tentar enviar uma mensagem que contenha conteúdo proibido:
        1. O sistema exibe uma mensagem informando que a mensagem não pode ser enviada devido a restrições de conteúdo.
        2. O usuário é solicitado a reformular sua mensagem.

### Requisitos Especiais:
- O sistema deve garantir que todas as mensagens sejam enviadas e recebidas em tempo real sem
necessidade de recarregar a página.
- A implementação deve utilizar WebSockets ou uma tecnologia similar para garantir a entrega em
tempo real.
- O sistema deve garantir a criptografia de mensagens para manter a segurança e a privacidade dos
usuários.
- O tempo de resposta do sistema deve ser mínimo, garantindo uma experiência de usuário fluida.