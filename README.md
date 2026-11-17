# WireGuard con Docker

## Descripción
Este proyecto consiste en la implementación de una VPN utilizando WireGuard mediante Docker y Docker Compose.

## Tecnologías utilizadas
- Ubuntu
- Docker
- Docker Compose
- WireGuard
- Linux

## Configuración del servidor
Se utilizó la imagen LinuxServer de WireGuard para crear un servidor VPN.

Los parámetros principales fueron:
- Puerto: 51820 UDP
- Número de clientes: 2
- Subred interna: 10.13.13.0
- Zona horaria: America/Mexico_City

## Clientes
Se generaron dos clientes:
- Peer 1: 10.13.13.2
- Peer 2: 10.13.13.3

## Pruebas realizadas
Se verificó el funcionamiento mediante el comando:

```bash
sudo docker exec wireguard wg show
```

Los dos clientes realizaron correctamente el handshake con el servidor y registraron transferencia de datos.

## Comandos principales

Iniciar el servidor:

```bash
sudo docker compose up -d
```

Consultar los contenedores:

```bash
sudo docker ps
```

Consultar las conexiones:

```bash
sudo docker exec wireguard wg show
```

Detener el servidor:

```bash
sudo docker compose down
```

## Seguridad
Los archivos de configuración y las claves privadas se excluyen del repositorio mediante `.gitignore`.
