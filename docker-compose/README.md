# Cenário SPIRE em docker
## Subindo o cenário
1. Gerar certificados
```
go run gencerts.go server/ agent/
```
2. Subir o SPIRE server
```
docker-compose -f docker-compose.yaml up -d spire-server
```
3. Exportar o bundle do SPIRE server
```
docker-compose -f docker-compose.yaml exec -T spire-server /opt/spire/bin/spire-server bundle show > agent/bootstrap.crt
```
4. Subir o SPIRE agent
```
docker-compose -f docker-compose.yaml up -d spire-agent
```

### Entendendo o que foi feito




