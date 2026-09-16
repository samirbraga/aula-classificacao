# Aula prática de classificação

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/samirbraga/aula-classificacao/blob/HEAD/aula_classificacao.ipynb)

Clique em **Open in Colab** para carregar o notebook diretamente do GitHub, sem preparar um ambiente local.

- [Notebook com explicações, exercícios e resultados](aula_classificacao.ipynb)

Explore problemas de classificação binária, multiclasse e multirrótulo com os datasets Breast Cancer, Iris e Digits. O notebook apresenta regressão logística, k-NN, árvore de decisão e Naive Bayes, além de exercícios sobre matriz de confusão, métricas, desbalanceamento e curvas ROC e precisão–recall.

Execute as células na ordem e use os resultados para responder aos exercícios. No Colab, escolha **Arquivo → Salvar uma cópia no Drive** para guardar suas alterações.

## Ambiente com uv

Na pasta do projeto:

```powershell
uv sync --locked
```

O uv usa a versão Python indicada em `.python-version` e instala as dependências de `uv.lock` no ambiente `.venv`. A primeira sincronização precisa de acesso à internet; os datasets não precisam de download separado.

Para confirmar a instalação:

```powershell
uv run python -c "import sklearn; print(sklearn.__version__)"
```

### VS Code

Abra a pasta do projeto no VS Code, para que ele carregue as configurações de `.vscode`. Use as extensões **Python**, **Pylance** e **Jupyter**, recomendadas pelo projeto.

1. Pressione `Ctrl+Shift+P`, execute **Python: Select Interpreter** e selecione o Python de `.venv`. No Windows, o caminho é `.venv/Scripts/python.exe`; no Linux/macOS, `.venv/bin/python`. Se não aparecer, use **Enter interpreter path...** para localizar o executável.
2. Abra `aula_classificacao.ipynb`. No seletor de kernel no canto superior direito, escolha **Select Another Kernel... → Python Environments...** e selecione o mesmo `.venv`.
3. Se os imports continuarem sublinhados, salve o notebook e execute **Developer: Reload Window** pela paleta de comandos.

O interpreter selecionado orienta a análise do Pylance; o kernel executa as células. Ambos devem usar o ambiente do projeto. A configuração `python.defaultInterpreterPath` indica o `.venv` como padrão, mas não substitui uma seleção já salva no VS Code. Consulte a [documentação de interpreters](https://code.visualstudio.com/docs/python/settings-reference) e a [seleção de kernels](https://code.visualstudio.com/docs/datascience/jupyter-kernel-management).

O caminho padrão em `.vscode/settings.json` aponta explicitamente para o executável no Windows. No Linux/macOS, ajuste-o para `${workspaceFolder}/.venv/bin/python`.

Se os avisos aparecerem na visualização de alterações do Git, abra `aula_classificacao.ipynb` pelo **Explorador de Arquivos do VS Code** (`Ctrl+Shift+E`). A cópia usada na comparação do Git pode ser analisada com um interpreter diferente do arquivo do projeto.

Para conferir o kernel ativo, execute em uma célula:

```python
import sys
print(sys.executable)
```

O caminho exibido deve apontar para o Python dentro de `.venv`. Depois, execute as células do notebook na ordem.

O botão no início deste README abre o notebook da branch padrão do repositório no Colab. Para reproduzir o ambiente definido neste projeto no seu computador, use os comandos com uv acima.

`pyproject.toml` declara as dependências; `uv.lock` fixa as versões resolvidas. O grupo `dev` contém as ferramentas de execução e validação do notebook.
