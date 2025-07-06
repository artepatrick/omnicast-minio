# MCP Servers Configuration

Este projeto está configurado com múltiplos **MCP Servers** para facilitar o desenvolvimento e gerenciamento da infraestrutura MinIO no Fly.io.

## Servers Configurados

### 1. Sequential Thinking MCP
Uma ferramenta poderosa para resolução de problemas complexos através de um processo de pensamento estruturado.

## O que é o Sequential Thinking MCP?

O Sequential Thinking MCP é um servidor que fornece uma ferramenta para resolução dinâmica e reflexiva de problemas através de um processo de pensamento estruturado.

### Funcionalidades

- **Quebra problemas complexos** em etapas gerenciáveis
- **Revisa e refina** pensamentos conforme o entendimento se aprofunda
- **Ramifica** em caminhos alternativos de raciocínio
- **Ajusta dinamicamente** o número total de pensamentos
- **Gera e verifica** hipóteses de solução

## Como usar

### No VS Code

1. **Instalação automática**: A configuração já está definida no arquivo `.vscode/mcp.json`
2. **Reinicie o VS Code** para carregar a nova configuração
3. **Use a ferramenta** `sequential_thinking` em suas conversas com Claude

### Configuração Manual (se necessário)

Se preferir configurar manualmente, adicione o seguinte ao seu `settings.json` do VS Code:

```json
{
  "mcp": {
    "servers": {
      "sequential-thinking": {
        "command": "npx",
        "args": [
          "-y",
          "@modelcontextprotocol/server-sequential-thinking"
        ]
      }
    }
  }
}
```

## Parâmetros da Ferramenta

- `thought` (string): O passo atual do pensamento
- `nextThoughtNeeded` (boolean): Se outro passo de pensamento é necessário
- `thoughtNumber` (integer): Número atual do pensamento
- `totalThoughts` (integer): Total estimado de pensamentos necessários
- `isRevision` (boolean, opcional): Se isso revisa pensamentos anteriores
- `revisesThought` (integer, opcional): Qual pensamento está sendo reconsiderado
- `branchFromThought` (integer, opcional): Número do pensamento de ramificação
- `branchId` (string, opcional): Identificador da ramificação
- `needsMoreThoughts` (boolean, opcional): Se mais pensamentos são necessários

## Casos de Uso Ideais

- **Problemas complexos** que precisam ser divididos em etapas
- **Planejamento e design** com espaço para revisão
- **Análises** que podem precisar de correção de curso
- **Problemas** onde o escopo completo pode não estar claro inicialmente
- **Tarefas** que precisam manter contexto ao longo de múltiplos passos
- **Situações** onde informações irrelevantes precisam ser filtradas

## Exemplo de Uso

```
Claude, use o sequential_thinking para analisar como otimizar a configuração do MinIO no Fly.io para melhor performance.
```

## Desabilitar Logs

Para desabilitar o log de informações de pensamento, defina a variável de ambiente:
```
DISABLE_THOUGHT_LOGGING=true
```

### 2. File System MCP
Permite manipulação avançada de arquivos e diretórios, útil para:
- Criar e modificar arquivos de configuração
- Organizar estrutura de projetos
- Gerenciar arquivos de deploy

### 3. GitHub MCP
Integração com repositórios GitHub para:
- Criar e gerenciar issues
- Fazer commits e pull requests
- Revisar código
- Gerenciar releases

### 4. Docker MCP
Gerenciamento de containers Docker para:
- Listar e gerenciar containers
- Executar comandos em containers
- Monitorar logs
- Gerenciar imagens

## Como usar

### No VS Code

1. **Instalação automática**: A configuração já está definida no arquivo `.vscode/mcp.json`
2. **Reinicie o VS Code** para carregar a nova configuração
3. **Use as ferramentas** disponíveis em suas conversas com Claude

### Exemplos de Uso

```bash
# Sequential Thinking para análise de problemas
"Claude, use o sequential_thinking para analisar como otimizar a configuração do MinIO"

# File System para criar arquivos
"Claude, use o filesystem para criar um script de backup"

# GitHub para gerenciar issues
"Claude, use o github para criar uma issue sobre otimização de performance"

# Docker para gerenciar containers
"Claude, use o docker para listar containers em execução"
```

## Alternativa com Docker

Se preferir usar Docker em vez de NPX, você pode alterar a configuração para:

```json
{
  "servers": {
    "sequential-thinking": {
      "command": "docker",
      "args": [
        "run",
        "--rm",
        "-i",
        "mcp/sequentialthinking"
      ]
    }
  }
}
``` 