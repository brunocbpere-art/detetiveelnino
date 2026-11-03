# Detetives da Notícia — 6º ano

Aplicativo educativo em Python/Streamlit para comparar duas reportagens sobre o mesmo acontecimento e avaliar a fidedignidade das informações.

## Correção visual (novembro de 2026)

Esta versão estabelece uma paleta clara para toda a aplicação, incluindo barra lateral, campos de texto e textarea, caixas de seleção e botões de rádio. Foram adicionados estilos para os contêineres BaseWeb que o Streamlit utiliza internamente e que não recebiam a correção anterior. O arquivo `.streamlit/config.toml` define o tema claro.

## Executar localmente

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Publicar/atualizar no Streamlit Community Cloud

1. Extraia os arquivos deste ZIP.
2. Envie para a **raiz** do mesmo repositório no GitHub os arquivos `app.py`, `requirements.txt`, `README.md` e a pasta `.streamlit` com `config.toml`.
3. No Streamlit Community Cloud, o arquivo principal deve ser `app.py`.
4. Após a atualização, recarregue a página com `Ctrl + Shift + R`. Se a interface antiga persistir, reinicie o aplicativo no painel do Streamlit.

**Importante:** envie o arquivo oculto `.streamlit/config.toml`! Apenas substituir o app.py pode manter um tema incorreto.

## Testes

- `python -m py_compile app.py` verifica sintaxe.
- `python test_simulacao.py` simula as rotas básicas de aluno e professor sem instalar Streamlit.
- É necessário executar um teste visual real no navegador, pois esta simulação não garante o resultado final do CSS em cada versão do Streamlit.

## Uso em sala

Os dois textos iniciais são **fictícios** e devem ser tratados como exemplos de exercício, não como reportagens reais. O modo professor altera apenas a sessão atual, sem persistência para a turma e sem autenticação. Os alunos podem baixar um JSON com suas respostas; o aplicativo não armazena respostas centralizadamente.
