# Omnicast MinIO

Deploy do MinIO no Fly.io com configuração de alta disponibilidade.

## Configuração

### 1. Criar os volumes no Fly.io

```bash
# Criar os volumes para armazenamento persistente
flyctl volumes create omnicast_minio_data_1 --size 10 --region gru
flyctl volumes create omnicast_minio_data_2 --size 10 --region gru
```

### 2. Configurar as credenciais

Edite o arquivo `fly.toml` e substitua:
- `SEU_ACCESS_KEY` por uma chave de acesso segura
- `SEU_SECRET_KEY` por uma chave secreta segura

Exemplo:
```toml
[env]
  MINIO_ACCESS_KEY = "minioadmin"
  MINIO_SECRET_KEY = "minioadmin123"
  MINIO_BROWSER    = "on"
```

### 3. Deploy

```bash
flyctl deploy
```

### 4. Verificar o status

```bash
flyctl status
flyctl logs
```

## Acessos

- **API MinIO**: `https://omnicast-minio.fly.dev` (porta 80/443)
- **Console Web**: `https://omnicast-minio.fly.dev:9001`

## Configuração do MinIO

O MinIO está configurado com:
- **Erasure Coding**: 2 drives para redundância de dados
- **Console Web**: Habilitado na porta 9001
- **HTTPS**: Forçado para todas as conexões
- **Health Checks**: Configurados para monitoramento

## Volumes

- `/export1`: Primeiro volume de dados
- `/export2`: Segundo volume de dados

## Comandos úteis

```bash
# Ver logs em tempo real
flyctl logs --follow

# Acessar o shell do container
flyctl ssh console

# Escalar a aplicação
flyctl scale count 1

# Ver informações dos volumes
flyctl volumes list
``` 