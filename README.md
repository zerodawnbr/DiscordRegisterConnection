<p align="center"> <img src="https://github.com/zerodawnbr/zerodawntoolbox/blob/main/imgs/banner.jpg" alt="Banner Zero Dawn"> </p>


![Banner do Mod](https://github.com/zerodawnbr/zerodawntoolbox/blob/main/imgs/zerodawntoolboxreigistroconexao.jpg)


# Registros automáticos de entrada e saída de jogadores

Este recurso permite que o servidor registre automaticamente quando os jogadores entram ou saem do jogo, salvando os dados no **profile do servidor** (JSON) e enviando notificações para um canal configurado no **Discord**.

Isso garante monitoramento em tempo real e histórico detalhado de todas as conexões do servidor.


---

## 🔍 Informações registradas

- **SteamID** do jogador  
- **Nome do jogador**  
- **Localização no mapa**  
- **Horário de entrada e saída**

---

## Arquivo de configuração (`config.json`)

O arquivo de configuração fica na pasta do profile do servidor e define o canal do Discord, o token do bot e informações do mapa:

Ao iniciar pela primeira vez, será criado o arquivo **config.json** na pasta **$profile:/ZeroDawnBRCoreTools/DiscordRegisterConnection/**

```json
{
    "id": "13998505703481111111",
    "token": "lhEn07LSntSAB3fNeof619yCP5kmnVQG279uTDorhsEu7HgYAoQHke2jisRwm0",
    "ServerName": "ZeroDawnBR - Livonia",
    "webservicephp": "",
    "mapa": "https://www.izurvive.com/livoniaHiking/",
    "zoommapa": "6",
    "enablediscord": 1
}
```
## Explicação dos campos

| Campo              | Descrição                                                                 | Valor padrão / Exemplo |
|-------------------|---------------------------------------------------------------------------|----------------------|
| **id**            | ID do canal do Discord onde as mensagens serão enviadas                  | `"13998505703481111111"` |
| **token**         | Token de autenticação do bot                                             | `"lhEn07LSntSAB3fNeof619..."` |
| **ServerName**    | Nome do servidor mostrado nas mensagens                                  | `"ZeroDawnBR - Livonia"` |
| **webservicephp** | URL de um webservice externo (opcional)                                  | `""` |
| **mapa**          | Link do mapa interativo do servidor                                      | `"https://www.izurvive.com/livoniaHiking/"` |
| **zoommapa**      | Nível de zoom padrão do mapa                                             | `"6"` |
| **enablediscord** | Habilita envio de registros para o Discord (`1` = sim, `0` = não)        | `1` |

### Exemplo visual

- **Screenshot do arquivo JSON gerado**:  
![Configuração JSON](https://github.com/zerodawnbr/zerodawntoolbox/raw/main/imgs/jsonconexaousuarios.png)

A cada conexão ou desconexão é registrado um arquivo fisico com o steamID do jogador no servidor e no discord (desde que o atributo enablediscord seja igual a 1)

```json
[
    {
        "BohemiaID": "uTSOyJPPea4tYly8LAXd92npXV2eDMWi",
        "Player": "Joagador1",
        "Action": "Connected",
        "SteamID": "123456789868988100",
        "Position": "11155.7, 180.096, 11406.1",
        "CurrentDateTimeUTC": "11:40",
        "CurrentDateUTC": "2025-08-24"
    },
    {
        "BohemiaID": "uTSOyJPPea4tYly8LAXd92npXV2eDMWi=",
        "Player": "Joagador1",
        "Action": "Disconnected",
        "SteamID": "123456789868988100",
        "CurrentDateUTC": "2025-08-24",
        "CurrentDateTimeUTC": "11:41",
        "Position": "11155.7, 180.096, 11406"
    },
```

<br><br><p align="center"> <img src="https://github.com/zerodawnbr/zerodawntoolbox/blob/main/imgs/banner.jpg" alt="Banner Zero Dawn"> </p>
