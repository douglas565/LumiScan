# LumiScan AI - Reconhecimento de Luminárias Offline

LumiScan AI é uma ferramenta robusta e focada em privacidade para o reconhecimento automatizado de luminárias e pontos de iluminação. O sistema utiliza uma combinação de OCR (Reconhecimento Óptico de Caracteres) no navegador e Inteligência Artificial local para extrair modelos e potências de imagens, funcionando de forma 100% offline.


## 🚀 Funcionalidades Principais

- **Processamento em Lote:** Carregue pastas inteiras de fotos de vistorias de uma só vez.
- **IA Local (Ollama):** Integração nativa com Ollama (modelo LLaVA) para análise visual avançada sem enviar dados para a nuvem.
- **OCR Híbrido:** Utiliza Tesseract.js para leitura rápida de etiquetas e placas de identificação.
- **Aprendizado Contínuo:** O sistema aprende com as correções manuais do usuário, melhorando a precisão em detecções futuras por similaridade.
- **Exportação Flexível:** Gere relatórios em CSV ou JSON prontos para integração em planilhas ou sistemas de gestão.
- **Interface Desktop:** Desenvolvido para rodar como um aplicativo desktop leve via Electron.

## 🛠️ Tecnologias Utilizadas

- **Frontend:** React 18 + TypeScript + Vite
- **Estilização:** Tailwind CSS
- **OCR:** Tesseract.js
- **IA Vision:** Ollama (LLaVA) / Google Gemini (opcional)
- **Desktop:** Electron
- **Animações:** Framer Motion (Motion)

## 📦 Pré-requisitos

Para utilizar o LumiScan com o máximo de potencial (análise por IA), você precisará do **Ollama** instalado localmente:

1. Baixe o Ollama em [ollama.com](https://ollama.com).
2. Após instalar, execute o comando para baixar o modelo de visão:
   ```bash
   ollama run llava
   ```

## ⚙️ Instalação e Desenvolvimento

1. **Clonar o repositório:**
   ```bash
   git clone https://github.com/seu-usuario/lumiscan-offline.git
   cd lumiscan-offline
   ```

2. **Instalar dependências:**
   ```bash
   npm install
   ```

3. **Rodar em modo de desenvolvimento (Web):**
   ```bash
   npm run dev
   ```

4. **Rodar como App Desktop (Electron):**
   ```bash
   npm run electron:dev
   ```

## 🏗️ Build e Distribuição

Para gerar o executável (.exe):

```bash
npm run build:exe
```

O instalador será gerado na pasta `/release`.

## 🧠 Como funciona a detecção?

1. **Seleção de Imagem:** O sistema analisa o grupo de fotos de um ponto e seleciona a imagem com melhor nitidez/iluminação.
2. **Extração de Texto:** O Tesseract.js varre a imagem em busca de palavras-chave como "W", "Watts", "LED", "Model".
3. **Análise de IA:** 
   - **Ollama (Local):** Caso o Ollama esteja ativo, a imagem é enviada para o modelo LLaVA local.
   - **Gemini (Nuvem):** O sistema também suporta integração com Google Gemini para análises de alta precisão quando houver conexão.
4. **Validação:** O resultado é comparado com o banco de dados de "Treinamento" (correções anteriores).
5. **Revisão:** Itens com baixa confiança são marcados para revisão manual do usuário.

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---
Desenvolvido para vistorias técnicas e inventários de iluminação pública/privada.
