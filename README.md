# HAProxy Load Balancer

Bem-vindo ao repositório `haproxy-load-balancer`! Este projeto demonstra a configuração e uso de HAProxy e NGINX para balanceamento de carga de servidores web. A configuração inclui a utilização de Docker para facilitar a implantação e gerenciamento dos serviços.

## 📚 Visão Geral

O projeto configura uma arquitetura de balanceamento de carga utilizando as seguintes tecnologias:

### HAProxy

**HAProxy** é um balanceador de carga de alto desempenho que distribui o tráfego para os servidores NGINX.

### NGINX

 <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nginx/nginx-original.svg" width="48" height="48"/>

**NGINX** é um servidor web e proxy reverso que pode ser configurado para balanceamento de carga e servir conteúdo estático.

### Docker

 <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-original.svg" width="48" height="48"/>
 
**Docker** é uma plataforma para desenvolver, enviar e executar aplicações em containers, facilitando a configuração e o gerenciamento dos serviços.

## 🚀 Começando

### Pré-requisitos

Certifique-se de ter os seguintes requisitos instalados:
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Instalação e Execução

1. **Clone o repositório:**

    ```bash
    git clone https://github.com/seu-usuario/haproxy-load-balancer.git
    cd haproxy-load-balancer
    ```

2. **Construa e inicie os containers:**

    ```bash
    docker-compose up --build
    ```

3. **Acesse o balanceador de carga:**

    O HAProxy estará escutando na porta `8080`. Acesse no navegador:

    ```
    http://localhost:8080
    ```

## 🛠️ Estrutura do Projeto

- `docker-compose.yml`: Arquivo de configuração do Docker Compose que define os serviços e redes.
- `haproxy_image/`: Pasta contendo a configuração do HAProxy.
  - `haproxy.cfg`: Arquivo de configuração do HAProxy.
- `nginx_image/`: Pasta contendo a configuração do NGINX.
  - `nginx.conf`: Arquivo de configuração do NGINX.

## 🔧 Configuração

### HAProxy

- **Porta de Escuta:** 80
- **Balanceamento:** Round-robin entre os servidores NGINX.

### Servidores Web

- **Portas:** 80
- **Conteúdo:** Servem arquivos estáticos e páginas dinâmicas.

## 📈 Testando o Balanceamento

Para testar o balanceamento de carga, você pode usar ferramentas de estresse como `ab` (Apache Benchmark), `wrk`, ou `siege` para enviar requisições para o HAProxy e verificar a distribuição entre os servidores NGINX.

### Exemplo com `ab`:

```bash
ab -n 1000 -c 10 http://localhost:8080/
