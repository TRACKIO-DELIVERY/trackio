## TrackIO - Serviço de Gerenciamento de Pedidos

Esse repositório reúne todos os projetos através da utilização de *submodules* do GitHub, apontando para uma determinada referência do código.


Para inicar, clone o projeto e rode os seguintes comandos.


```bash
git submodule init
```

```bash
git submodule update
```

Atualize todos os módulos para a branch padrão
```bash
git submodule update --remote --merge
```


Use o *env.template* como base e substitua com suas variáveis
Crie os volumes do Loki com permissão de usuário necessária.


```bash
docker run --rm -v loki_data:/loki alpine sh -c "mkdir -p /loki/index /loki/cache /loki/chunks /loki/wal /loki/compactor && chown -R 10001:10001 /loki"
```


Execute os serviços através do compose
```bash
docker-compose up -d --build
```