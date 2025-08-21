### Prompt Optimizer

Prompt Optimizer is a versatile AI prompt optimization tool designed to enhance the quality and effectiveness of AI outputs. It provides a comprehensive suite of features for refining prompts, testing their performance, and managing AI models and historical interactions.

#### Key Features
*   **Intelligent Prompt Optimization:** Optimizes both system and user prompts, supporting multi-round iterative improvements to achieve desired AI responses.
*   **Multi-Model Integration:** Connects with various mainstream AI models, including OpenAI, Gemini, DeepSeek, Zhipu AI, and SiliconFlow, as well as custom OpenAI-compatible APIs.
*   **Real-time Testing & Comparison:** Allows users to test optimized prompts against original ones and compare results side-by-side.
*   **Data Management:** Manages AI model configurations, prompt templates, and historical optimization records, with capabilities for data import and export.
*   **Flexible Deployment:** Available as a web application, desktop application, Chrome extension, and Docker container, catering to diverse user preferences and environments.
*   **Access Control:** Offers optional password protection for web deployments to secure access.
*   **MCP Protocol Support:** Integrates with Model Context Protocol (MCP) compatible applications for enhanced interoperability.
*   **Proxy Functionality:** Includes built-in proxy capabilities to resolve Cross-Origin Resource Sharing (CORS) issues, particularly for web and Docker deployments.

#### Data Handling & Security
*   **Client-Side Processing:** For web and Chrome extension versions, all data processing occurs on the client-side, with direct interaction between the user's browser and AI service providers, ensuring privacy.
*   **Local Storage:** Desktop applications store data locally on the user's machine.
*   **No Intermediate Servers:** Unless explicitly configured for proxying (e.g., via Vercel or Docker proxy), no intermediate servers handle user prompts or API keys.

#### Inputs
*   **User Interface (UI):** Text prompts for optimization, iteration, and testing; configuration settings for models and templates; user preferences.
*   **Files:** JSON files for importing application data (models, templates, history, preferences).
*   **HTTP/S Requests:** For web and Docker deployments, handles incoming API requests for proxying and streaming to AI service providers.

#### Outputs
*   **UI Display:** Optimized prompts, AI model responses, test results, historical records, and configuration interfaces.
*   **Files:** Exported JSON files containing all application data.
*   **HTTP/S Responses:** For web and Docker deployments, forwards AI model responses (including streamed content) back to the client.

#### Configuration
The agent can be configured using environment variables, primarily for API keys and deployment-specific settings:
*   `PORT`: Configures the listening port for the Node.js proxy server.
*   `STREAM_TIMEOUT`, `PROXY_TIMEOUT`: Set timeout durations (in milliseconds) for stream-based and standard proxy requests, respectively.
*   `NODE_ENV`: Indicates the current environment (e.g., `development`, `production`).
*   `VITE_OPENAI_API_KEY`, `VITE_GEMINI_API_KEY`, `VITE_DEEPSEEK_API_KEY`, `VITE_SILICONFLOW_API_KEY`, `VITE_ZHIPU_API_KEY`: Store API keys for various AI providers.
*   `VITE_CUSTOM_API_KEY`, `VITE_CUSTOM_API_BASE_URL`, `VITE_CUSTOM_API_MODEL`: Store default settings for generic OpenAI-compatible custom API services.
*   `VITE_CUSTOM_API_KEY_{suffix}`, `VITE_CUSTOM_API_BASE_URL_{suffix}`, `VITE_CUSTOM_API_MODEL_{suffix}`: Dynamic variables for configuring multiple custom API models.
*   `ACCESS_PASSWORD`: Sets an optional password for web application access control.
*   `GITHUB_REPOSITORY`, `DEV_REPO_OWNER`, `DEV_REPO_NAME`: Used for desktop application auto-update configuration.
*   `VITE_VERCEL_DEPLOYMENT`: A boolean flag indicating if the application is deployed on Vercel.
*   `MCP_DEFAULT_MODEL_PROVIDER`, `MCP_LOG_LEVEL`: Configure settings for the Model Context Protocol (MCP) server.
*   `OLLAMA_ORIGINS`, `OLLAMA_HOST`: Used to configure CORS and host address for local Ollama instances.
*   `ELECTRON_BUILD`: A flag used during the build process for the web package when it's being prepared for Electron.