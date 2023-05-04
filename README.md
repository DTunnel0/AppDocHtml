# DTunnel - Documentação da API

Esta é a documentação da API do sistema de configuração da aplicação DTunnel.
Aqui estão listados todos os métodos disponíveis com suas respectivas descrições.

**É importante lembrar que esses métodos devem ser chamados a partir do código JavaScript para poderem ser utilizados. Portanto, se você estiver desenvolvendo um layout que utilize esses métodos, certifique-se de chamar os métodos corretamente a partir do código JavaScript para que eles funcionem adequadamente**.

## Configuração

### DtSetConfig.execute(id)

Método utilizado para definir a configuração padrão do app.

Parâmetros:

- id (integer): Identificador da configuração a ser setada.

Retorno: void

Exemplo:

```html
<script>
    DtSetConfig.execute(1000)
</script>
```

### DtGetConfigs.execute()

Método utilizado para obter todas as configurações disponíveis.

Parâmetros: nenhum

Retorno: string (json contendo todas as configurações)

Exemplo:

```json
[
    {
        "id": 1000,
        "name": "Categoria 01",
        "sorter": 1,
        "color": "#FFFFFF",
        "items": [
            {
                "id": 1000,
                "name": "Configuração 01",
                "description": "Descricão da configuração",
                "mode": "SSH_DIRECT",
                "sorter": 1,
                "icon": "https://example.com/assets/icon1.png"
            },
            {
                "id": 1001,
                "name": "Configuração 02",
                "description": "Descricão da configuração",
                "mode": "SSH_DIRECT",
                "sorter": 2,
                "icon": "https://example.com/assets/icon2.png"
            },
        ]
    }
]
```

### DtGetDefaultConfig.execute()

Método utilizado para obter a configuração padrão atual do app.

Parâmetros: nenhum

Retorno: string (configuração padrão)

Exemplo:

```json
{
    "id": 1000,
    "name": "Configuração 01",
    "description": "Descricão da configuração",
    "mode": "SSH_DIRECT",
    "sorter": 1,
    "icon": "https://example.com/assets/icon1.png"
}
```

### DtExecuteVpnStop.execute()

Método utilizado para parar o serviço de VPN.

Parâmetros: nenhum

Retorno: void

### DtExecuteDialogConfig.execute()

Método utilizado para mostrar o diálogo nativo de configuração.

Parâmetros: nenhum

Retorno: void

## Usuário

### DtUsername.get()

Método utilizado para obter o nome do usuário atual.

Parâmetros: nenhum

Retorno: string (nome do usuário)

### DtUsername.set(username)

Método utilizado para definir o nome do usuário.

Parâmetros:

- username (string): Novo nome de usuário.

Retorno: void

### DtPassword.get()

Método utilizado para obter a senha atual.

Parâmetros: nenhum

Retorno: string (senha atual)

### DtPassword.set(password)

Método utilizado para definir a senha.

Parâmetros:

- password (string): Nova senha.

Retorno: void

### DtUuid.get()

Método utilizado para obter o uuid atual (v2ray).

Parâmetros: nenhum

Retorno: string (uuid)

### DtUuid.set(uuid)

Método utilizado para definir o uuid (v2ray).

Parâmetros:

- uuid (string): Novo uuid.

Retorno: void

## Logs

### DtGetLogs.execute()

Método utilizado para obter todos os logs.

Parâmetros: nenhum

Retorno: string (json contendo todos os logs)

Exemplo:

```javascript
[
    {
        "00:00:00": "MESSAGE"
    }
]
```

### DtClearLogs.execute()

Método utilizado para limpar todos os logs.

Parâmetros: nenhum

Retorno: void

### DtShowLoggerDialog.execute()

Método utilizado para mostrar o diálogo nativo de logs.

Parâmetros: nenhum

Retorno: void

## VPN

### DtExecuteVpnStart.execute()

Método utilizado para iniciar o serviço de VPN.

Parâmetros: nenhum

Retorno: void

### DtGetVpnState.execute()

Método utilizado para obter o status atual da VPN.

Parâmetros: nenhum

Retorno: string (status atual)

Exemplo:**```CONNECTED, DISCONNECTED, CONNECTING, STOPPING, NO_NETWORK, AUTH, AUTH_FAILED```**

## Atualização e checagem

### DtStartAppUpdate.execute()

Método utilizado para buscar atualizações.

Parâmetros: nenhum

Retorno: void

### DtStartCheckUser.execute()

Método utilizado para fazer a checagem do usuário.

Parâmetros: nenhum

Retorno: void

## Tradução

### DtTranslateText.execute(label)

Método utilizado para pegar um texto a partir de um label.

Parâmetros:

- label (string): Label do texto a ser traduzido.

Retorno: string (texto traduzido)

Exemplo:

``` html
<script>
    const text = DtTranslateText.execute('LBL_START')
    console.log(text) // INICAR
</script>
```

## Limpeza e configurações do app

### DtCleanApp.execute()

Método utilizado para limpar todos os dados do aplicativo.

Parâmetros: nenhum

Retorno: void

### DtGetAppConfig.execute(name)

Método utilizado para obter uma configuração específica do aplicativo.

Parâmetros:

- name (string): Nome da configuração.

Retorno: string (valor da configuração)

### DtIgnoreBatteryOptimizations.execute()

Método utilizado para ignorar a economia de bateria.

Parâmetros: nenhum

Retorno: void

### DtStartApnActivity.execute()

Método utilizado para iniciar a atividade de APN.

Parâmetros: nenhum

Retorno: void

### DtStartWebViewActivity.execute()

Método utilizado para iniciar a atividade de página WebView.

Parâmetros: nenhum

Retorno: void

### DtStartWebViewActivity.execute(url)

Método utilizado para iniciar a atividade de página WebView a partir de uma URL.

Parâmetros:

- url (string): URL da página.

Retorno: void

Exemplo:

```html
<script>
    DtStartWebViewActivity.execute('https://example.com')
</script>
```

### DtStartRadioInfoActivity.execute()

Método utilizado para iniciar a atividade de informações do rádio (em breve).

Parâmetros: nenhum

Retorno: void
