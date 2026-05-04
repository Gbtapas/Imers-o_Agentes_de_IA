AI Agent Service Desk: Triagem e RAG com LangGraph 

Este projeto consiste em um sistema autônomo de triagem para Service Desk, desenvolvido para gerenciar chamados e responder dúvidas sobre políticas internas utilizando Inteligência Artificial. O agente utiliza uma lógica de grafos de estado para decidir entre resolver uma dúvida automaticamente ou escalar para um atendimento humano.  

🛠️ Tecnologias Utilizadas 

LLM: Google Gemini 2.5 Flash.  

Orquestração de Fluxos: LangGraph e LangChain.  

Vector Database: FAISS (para busca por similaridade).  

Processamento de Dados: PyMuPDF para extração de PDFs corporativos.  

Validação de Dados: Pydantic para estruturação de saídas JSON.  

🧠 Arquitetura do Sistema 

O diferencial deste agente é a utilização de um StateGraph (Grafo de Estado) que orquestra o raciocínio do modelo em diferentes nós:  

Nó de Triagem: O primeiro contato analisa a intenção do usuário e classifica a urgência. Utiliza saídas estruturadas para garantir que o sistema sempre saiba para onde rotear a mensagem.  

Nó de Auto-Resolução (RAG): Se a dúvida for técnica, o agente busca o contexto em uma base de conhecimentos (PDFs) via embeddings. Ele só responde se encontrar a informação exata no documento, evitando alucinações.  

Nó de Ação Final: Dependendo da análise, o sistema gera a resposta final ao usuário, solicita informações pendentes ou simula a abertura de um chamado técnico com os metadados necessários.  

🚀 Como Executar 

Chave de API: Certifique-se de ter a variável GEMINI_API_KEY configurada no seu ambiente.  

Base de Conhecimento: Insira os documentos de política em PDF no diretório especificado para alimentar o banco vetorial.  

Dependências: 

Bash: 
pip install langgraph langchain-google-genai google-generativeai faiss-cpu pymupdf pydantic 
 
Execução: Rode o notebook ou script principal para iniciar o loop de interação do agente. 

 
