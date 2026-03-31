# 🤖 Multi-Provider AI Chat | Next.js + Express + LangChain

Este projeto é um assistente de chat Full Stack que utiliza o padrão de projeto **Factory** para alternar dinamicamente entre diferentes provedores de Inteligência Artificial. 

O diferencial técnico desta implementação é o **desacoplamento**: a aplicação não depende de um único modelo, permitindo a troca de provedor (Gemini, OpenAI ou Groq) apenas alterando uma variável de ambiente, sem necessidade de refatorar o código de negócio.

## 🛠️ Diferenciais Técnicos

### **Agnosticismo de Provedor (Factory Pattern)**
Implementei uma lógica de inicialização no Backend que detecta automaticamente as chaves de API disponíveis ou segue uma diretriz forçada via `.env`:

- **Google Gemini**: Utilizando o modelo `gemini-1.5-flash` (Alta performance e custo zero).
- **OpenAI**: Suporte para `gpt-4o-mini`.
- **Groq (Llama 3)**: Focado em baixíssima latência com o modelo `llama-3.1-8b-instant`.

### **Arquitetura Full Stack Moderno**
- **Frontend**: Desenvolvido em **Next.js 14+** com Tailwind CSS para uma UI limpa e componentes modernos.
- **Backend**: Servidor **Express** orquestrando as chamadas de IA via **LangChain JS**.
- **Segurança**: Implementação de Proxy no Backend para proteger as API Keys, garantindo que nunca sejam expostas no lado do cliente.

---

## 🚀 Como Executar o Projeto

### 1. Pré-requisitos
- Node.js instalado.
- Pelo menos uma chave de API (Google AI Studio, OpenAI ou Groq).

### 2. Configuração do Backend
Entre na pasta `/backend`, crie um arquivo `.env` (use o `.env.example` como base) e preencha suas chaves:
```env
PORT=3001
PROVIDER=gemini # Opções: gemini, openai, groq
GOOGLE_GENAI_API_KEY=sua_chave_aqui
OPENAI_API_KEY=sua_chave_aqui
GROQ_API_KEY=sua_chave_aqui
```

### 3. Instalação e Execução

# Terminal 1: Backend
cd backend
npm install
npm run dev

# Terminal 2: Frontend
cd frontend
npm install
npm run dev
