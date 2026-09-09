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
