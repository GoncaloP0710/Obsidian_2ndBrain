2024-08-31 00:30

Status: #done

Tags: [[Segurança e Confiabilidade]] [[Attacks]] 

# Classes de Ataques

## Ataques passivos
tenta-se obter informação existente no sistema sem afetar os seus recursos
Exemplos:
### Escutar (sniffing):
sondas passivas apenas escutam o tráfego numa rede com o objetivo de o ler. É muito difícil detetar um sniffer, já que se trata de um ataque completamente passivo
### Análise de tráfego (traffic analysis): 
escuta-se o tráfego e, embora não se consiga ler, obtém-se informação sobre o que está a ser enviado
### Vasculhar (snooping): 
vasculhar o interior de sistemas e repositórios de dados em busca de informação relativa a passwords, configurações, etc.
### Sondar (probing): 
sondas pesquisam sistemas em busca de informações e vulnerabilidades
## Ataques ativos
tenta-se alterar o funcionamento correto do sistema
Tentativas agressivas de entrar no sistema, para corromper a sua operação e/ou roubar, modificar ou mesmo destruir dados
### Spoofing
Situação em que uma pessoa ou sistema personifica outra entidade, podendo atuar em seu nome, conseguindo por exemplo falsificar dados
Spoofing aparece frequentemente ligado a email, IP, MAC
### Homem-no-Meio
Uma máquina maliciosa interceta a comunicação entre dois participantes, depois lê e/ou muda o seu conteúdo dinamicamente
### Vírus de Computador
Programas que se inserem dentro de um ou mais ficheiros e executam alguma ação maliciosa
Pedaço de código auto-replicável com algum outro código (usualmente malicioso) associado
Ciclo de vida de um vírus: adormecido/propagação/execução
### Worm de Computador
Programa que se copia de um computador para outro
Replica-se, espalhando-se pela rede ➔ consome recursos, mas tipicamente não infeta ficheiros
Ciclo de vida de um worm: adormecido/propagação/execução
### Bomba Lógica (Logic Bomb)
Programa que executa uma ação que impõe uma falha de segurança no sistema quando um evento externo ocorre
O código das bombas lógicas é geralmente embutido em programas legítimos
Tipicamente causam danos ao sistema
### Cavalo de Troia (Trojan)
Programa com um objetivo aberto (conhecido pelo utilizador) e um outro objetivo escondido (desconhecido pelo utilizador)
Basicamente o cavalo de Troia é um programa que aparentemente é legítimo e útil, mas que esconde funcionalidades com fins ilegítimos
### Zombie / Bot
Programa que secretamente permite o controlo de um computador ligado à rede
Permanece adormecido até ser ativado
A partir daí usa a máquina vítima para realizar tarefas de interesse do seu controlador
## Ataques externos
realizados por entidades fora do perímetro de segurança, por um utilizador não autorizado
## Ataques internos
realizados por uma entidade dentro do perímetro de segurança, possivelmente com alguns privilégios

# References

