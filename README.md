# Agentes de IA — saída estruturada com Pydantic

Como fazer um LLM responder em **JSON validado** em vez de texto livre — o primeiro passo para usar IA generativa
dentro de pipelines e sistemas. O mesmo problema (extrair título, ano, diretor, gênero e elenco de um filme) é resolvido
de duas formas, com o mesmo esquema Pydantic:

| Notebook | Abordagem |
|---|---|
| [saida_estruturada_google_genai.ipynb](saida_estruturada_google_genai.ipynb) | SDK oficial do Google (`google-genai`): o modelo Pydantic vai direto em `response_schema` e a resposta já volta como objeto (`response.parsed`). |
| [saida_estruturada_langchain.ipynb](saida_estruturada_langchain.ipynb) | LangChain: `PydanticOutputParser` + `ChatPromptTemplate` + `ChatGoogleGenerativeAI` encadeados com LCEL. |

## Como rodar

```bash
pip install google-genai langchain-core langchain-google-genai pydantic python-dotenv
echo "GEMINI_API_KEY=sua-chave" > .env   # a chave nunca vai para o repositório
jupyter notebook
```

**Tecnologias:** Python, Pydantic, Google Gemini (`gemini-2.5-flash-lite`), LangChain.

---
Autor: [Jefferson Marques da Silva](https://github.com/Jefferson019) · [LinkedIn](https://www.linkedin.com/in/jefferson-marques-da-silva-431606165)
