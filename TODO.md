# TODO - Transição arcane4-completo -> FisioSmart (sem migrações)

## A. Prompts e agentes (prioridade máxima)
- [ ] Editar `usuarios/agent.py`:
  - [ ] TriagemAgent: trocar semântica para Triagem Cinético-Funcional e retorno de cor conforme dor/incapacidade/limitação.
  - [ ] AssistentAgent (RAG):
    - [ ] Trocar persona para Fisioterapeuta Clínico (FisioSmart).
    - [ ] Remover tool FDA veterinário (`buscar_eventos_adversos_veterinarios`) do agente.
    - [ ] Manter streaming e gravação em `ContextRag` funcionando.
  - [ ] SecretariaAI: trocar persona para assistente da clínica FisioSmart via WhatsApp.
- [ ] Editar `prompts/prompt.py`:
  - [ ] Summary prompt: história clínica cinético-funcional (humano, EVA, limitação, região anatômica, lesões/cirurgias).
  - [ ] ExamAnalysis prompt: exames humanos (RM/RX/US musculoesquelético etc.).

## B. Views e tarefas
- [ ] Editar `usuarios/views.py`: trocar mensagens/strings relacionadas a “veterinária/triagem veterinária” para “FisioSmart/Triagem Cinético-Funcional”.
- [ ] Editar `usuarios/tasks.py`: trocar logs/strings para refletir fisioterapia (sem alterar a lógica do pipeline).

## C. Templates e branding
- [ ] Trocar branding e cabeçalhos:
  - [ ] `templates/partials/navbar.html`: “petcare/Petcare IA” -> “FisioSmart”.
  - [ ] `usuarios/templates/chat.html`, `clientes.html`, `paciente.html`: trocar “pet/veterinário” por “paciente humano/cliente/queixa principal” e ajustar placeholders.

## D. Configurações/ambiente
- [ ] Garantir que `.env.example` e comentários apontem para FisioSmart (somente comentário; sem mudar `OPENAI_API_KEY`).

## E. Validação
- [ ] Rodar `python manage.py makemigrations` (não será necessário se não mexer em models)
- [ ] Rodar `python manage.py migrate`
- [ ] Rodar `python manage.py runserver` e validar rotas principais e streaming.

