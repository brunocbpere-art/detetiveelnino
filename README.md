# Detetives da Notícia — 6º ano (versão corrigida)

App educacional em Python/Streamlit para comparar duas reportagens do mesmo acontecimento: fontes, autoria, data, evidências, seis questões de múltipla escolha com devolutiva e três reflexões escritas.

## Correção visual
Esta edição corrige o contraste dos textos das alternativas do **Painel 3**: adiciona tema claro em `.streamlit/config.toml` e estilo explícito para os textos dos botões de escolha. As alternativas deixam de aparecer quase brancas sobre o fundo claro.

## Publicar no Streamlit Community Cloud
1. Crie um repositório no GitHub e envie **o conteúdo desta pasta**, incluindo `app.py`, `requirements.txt` e a pasta oculta `.streamlit` com `config.toml`.
2. Em https://share.streamlit.io, escolha **Create app**, selecione o repositório e use `app.py` como arquivo principal.
3. Clique em **Deploy** e compartilhe o endereço do aplicativo.

## Testar localmente

```bash
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

## Utilização
- **Aluno(a):** examina os dois textos (exemplos fictícios), compara aspectos, responde questões e baixa respostas JSON.
- **Professor(a):** pode inserir transcrição, dados e print (PNG/JPG/WEBP) de cada reportagem e editar perguntas e respostas. **Essas alterações são temporárias e não são sincronizadas automaticamente com os aparelhos dos alunos**. Para publicar uma atividade personalizada para todos, altere os exemplos iniciais de `app.py` e publique nova versão.
- Questões do exemplo devem ser revistas sempre que as reportagens forem alteradas.
- Não há leitura automática de texto no print; transcreva as informações necessárias.
- Não há cadastro de alunos, armazenamento compartilhado de respostas nem autenticação de professor.

Evite inserir dados pessoais de alunos ou imagens sem autorização.

## Auditoria técnica (3 de novembro de 2026)
- Verificação de sintaxe com `python -m py_compile app.py`: aprovada.
- Simulação isolada dos caminhos: modo aluno, correção, modo professor, restauração, limpeza e produção do JSON: aprovada.
- Proteção dos títulos e dados das reportagens no HTML: `html.escape`.
- Links externos somente em URLs HTTP/HTTPS válidas.
- Tentativa de instalar Streamlit neste ambiente: indisponível porque o acesso ao índice de pacotes está bloqueado. **Não foi executado um navegador real nem Google Colab nesta revisão.**
- O modo professor **não possui autenticação**; não use o app publicado como um ambiente de avaliação oficial com dados pessoais ou notas.

### Testar no Google Colab
1. Faça upload do `app.py` e do `requirements.txt` para a sessão do Colab.
2. Execute:
```python
!pip install -r requirements.txt
!python -m py_compile app.py
!python -m streamlit run app.py --server.headless true --server.port 8501 > streamlit.log 2>&1 &
!sleep 5
!cat streamlit.log
```
3. A execução em Colab não fornece automaticamente um link público para o aplicativo. Para navegar e testar visualmente, publique no Streamlit Community Cloud conforme as instruções acima (recomendado), ou configure um túnel de acesso com medidas de segurança apropriadas.
