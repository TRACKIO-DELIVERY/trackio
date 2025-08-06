## TrackIO - Serviço de Gerenciamento de Pedidos

Esse repositório reúne todos os projetos através da utilização de *submodules* do GitHub, apontando para uma determinada referência do código.

### Passos para executar o TrackIO
-  Clone o projeto juntamente com as referências dos submodulos:

```bash
git clone --recurse-submodules https://github.com/TRACKIO-DELIVERY/trackio
```


*Para atualizar os submodules com referência à branch padrão utillize sempre:*
```bash
git submodule update --remote --merge
```
Use o *env.template* e substitua com suas variáveis


> INFO
> Antes de executar o compose, crie os volumes utilizados pelo loki e dê permissão necessária ao usuário (10001). Crie os volumes do Loki com permissão de usuário necessária.



```bash
docker run --rm -v loki_data:/loki alpine sh -c "mkdir -p /loki/index /loki/cache /loki/chunks /loki/wal /loki/compactor && chown -R 10001:10001 /loki"
```


- Execute os serviços através do compose
```bash
docker-compose up -d --build
```

Para entender sobre cada serviço.
<a href="https://github.com/TRACKIO-DELIVERY/infra/blob/main/readme.md"><p>infra</p></a>
<a href="https://github.com/TRACKIO-DELIVERY/message-broker/tree/main"><p>message-broker</p></a>
<a href="https://github.com/TRACKIO-DELIVERY/order-service/blob/main/README.md"><p>order-service</p></a>
<a href="https://github.com/TRACKIO-DELIVERY/tracking-service/blob/main/README.md"><p>tracking-service</p></a>
