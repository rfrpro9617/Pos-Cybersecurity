# Pos-Cybersecurity

Anotações da minha Pós-Graduação em Cybersecurity.

# Estrutura e funcionamento do protocolo TCP (Transmission Control Protocol)

- Protocolo orientado à conexões (mantém informações sobre cada conexão ativa).
- Entrega confiável, ordenada e livre de erros.
- Utilizado em aplicações críticas (navegação Web, envio de e-mails, transferência de arquivos).
- Controle de congestionamento: ajusta dinamicamente sua janela de envio com base na capacidade do receptor e nas condições da rede.
- Sacrifica desempenho em troca de confiabilidade e controle. Ideal para aplicações que não toleram perca de pacotes ou transmissão fora de ordem, mesmo que isso implique maior latência.

# Estrutura e funcionamento do protocolo UDP (User Datagram Protocol)

- Não orientado a conexão.
- Sem mecanismos de controle de conexão, verificação de entrega, ordenação ou retransmissão.
- Simplicidade e eficiência.
- Ideal para aplicações que requerem velocidade e latência mínima, mesmo que tolerem percas de pacotes.

 # Comparação entre TCP e UDP: diferenças, vantagens e aplicações

Ambos atuam na camada de transporte, no envio de dados entre processos que estão em execução em máquinas diferentes.

Um sistema bancário que transmite dados sensíveis de clientes deve utilizar TCP para garantir integridade e ordem dos
dados. Por outro lado, um jogo on-line ou uma videoconferência se beneficia do UDP, pois a latência baixa é mais importante do que a entrega perfeita de todos os pacotes.

OBS: um único pacote de rede transporta apenas uma fração minúscula de informação.

📦 O que realmente vem dentro de um pacote?

Um pacote de rede é como uma única pecinha de um quebra-cabeça de milhares de peças.

No vídeo/streaming: Um pacote contém apenas alguns pixels ou linhas de uma única imagem (frame). Um segundo de vídeo em alta definição é composto por cerca de 30 a 60 frames, e cada frame é dividido em dezenas de pacotes.

No jogo on-line: Um pacote contém apenas uma coordenada de posição milenar (ex: "Jogador X mudou a posição de 10.1 para 10.2") ou uma atualização de estado rápida. Jogos enviam de 30 a 128 desses pacotes por segundo (Tick Rate).

⏱️ O "Efeito Dominó" do TCP vs. O Descarte do UDP

A grande diferença entre os dois protocolos não é que o UDP "gosta" de perder dados, mas sim como eles reagem quando uma perda inevitável acontece na internet.

Cenário (Perda de 1 pacote)Protocolo | TCP (Banco)Protocolo | UDP (Jogo / Vídeo)
O que ele faz? | Para tudo e pede o pacote de novo. | Ignora o erro e processa o próximo pacote.
Comportamento | Nenhum pacote seguinte é entregue até o perdido chegar (bloqueio). | A fila continua andando em tempo real.
Impacto no Vídeo | O vídeo congela totalmente (buffering) por 1 ou 2 segundos. | Uma linha de pixels pisca por \(\frac{1}{60}\) de segundo (imperceptível).
Impacto no Jogo | Seu personagem trava no lugar e você sofre um "lag" enorme. | O jogo calcula a posição atualizada no pacote seguinte (um leve "teletransporte").

# Protocolo HTTP: requisições, respostas e comunicação na web

Viabiliza a comunicação cliente-servidor.
Segue o modelo cliente-servidor. O cliente envia uma requisição e aguarda uma resposta (html, json, xml).
Protocolo sem estado (stateless), o servidor não mantém informações sobre o cliente durante as interações. Isso reduz a carga do lado do servidor, mas exige o uso de técnicas como cookies, tokens e sessões para manter informações de autenticação, preferência e histórico.

# Segurança e performance em aplicações web: HTTPS, cache e cookies

