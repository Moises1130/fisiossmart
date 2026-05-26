# TODO - FisioSmart (arcane4-completo)

- [x] Atualizar suíte de testes: criar `FisioSmartPipelineTestCase` e mocks de agentes (Gemini) em `usuarios/tests.py`.
- [ ] Criar endpoint de agenda: `api_eventos_calendario` em `usuarios/views.py` + rota em `usuarios/urls.py`.
- [ ] Criar componente visual: `usuarios/templates/components/alerta_triagem.html`.
- [ ] Criar tela completa: `arcane4-completo/templates/agenda.html` com FullCalendar.
- [ ] Rodar `python manage.py test` e corrigir eventuais falhas.

## DevOps/Deploy

- [x] Unificar leitura de variáveis de ambiente em `core/settings.py` usando somente `os.getenv()` e garantir mapeamento `GOOGLE_API_KEY`.
- [x] Ajustar `SECRET_KEY` com fallback seguro apenas quando `DJANGO_DEBUG` estiver habilitado; levantar `ImproperlyConfigured` apenas em produção (Render).
- [x] Validar com `python manage.py check` e preparar comandos Git (PowerShell) para commit/push.


