# Testes

## Teste de Conexão

- Conecte um cliente à LAN e verifique se este recebe um endereço de IP 213.145.0.0/16.

No Linux:

``` sh
    ifconfig
```

No Windows:

``` sh
    ipconfig /all
```

- Na cliente LAN, utilize os comandos para verificar a conexão com o Gateway e com o Roteador do LDS

``` sh
    ping 213.145.0.1
    ping 192.168.133.1
```

## Teste de NAT

- No cliente LAN, tente acessar a internet:

``` sh
    ping 8.8.8.8
```

- No Gateway, veja as regra do pf em ação:

``` sh
    pfctl -s state
```

## Teste de DNAT

- Inicie um servidor TCP em um cliente LAN:

``` sh
    nc -l 8080
```

- Em um dispositivo na WAN, tente conectar à porta 80 do roteador:

``` sh
    telnet 192.168.133.X 80
```
