# AWS Cloud Project <image src="https://user-images.githubusercontent.com/12403699/234434276-e7cdcab8-c594-47a6-8862-7645e5740a2c.png" width="80" height="50">  
  
## Proposta de arquitetura para hospedagem de um WebSite na AWS.
  
## Tecnologias utilizadas  
  
- Amazon CloudFront

- Amazon Route 53
  
- Amazon S3 
  
- Amazon CloudWatch
  
## Objetivo

Desenvolvimento de um website (html, css, imagens) contendo os currículos do grupo e a implantação de um ou mais serviços na nuvem AWS, com rede de entrega de conteúdo, com baixa latência, com segurança, e armazenamento durável, para atender a demanda de 11 milhões de requisições por mês.  
  
## Arquitetura

<image src="https://github.com/deciocferreira/Cloud-Website-CV/assets/12403699/bc8efa3b-5ed5-4e40-bc62-a46ec14d595c" width="800" height="500">
       
## Fluxo da arquitetura
- O usuário acessa o website e faz uma solicitação de uma página HTML, imagem ou currículo.
- O DNS do domínio é gerenciado pelo Amazon Route 53.
- O Route 53 recebe a solicitação e direciona o tráfego para o Amazon CloudFront.
- O CloudFront atua como uma CDN (Content Delivery Network) e possui pontos de presença globalmente distribuídos.
- O CloudFront verifica se possui uma cópia em cache do conteúdo solicitado nos seus pontos de presença. Se tiver, ele entrega o conteúdo diretamente ao usuário, reduzindo a latência. 
  - Se o CloudFront não tiver uma cópia em cache do conteúdo solicitado, ele faz uma solicitação ao Amazon S3, onde os arquivos HTML, CSS, imagens e currículos estão armazenados.
- O Amazon S3 retorna o conteúdo solicitado para o CloudFront.
- O CloudFront recebe o conteúdo do S3 e, opcionalmente, pode aplicar funcionalidades adicionais, como compressão, redimensionamento de imagens ou autenticação, dependendo da configuração definida.
- O CloudFront entrega o conteúdo ao usuário através de um ponto de presença próximo geograficamente, minimizando a latência e proporcionando uma experiência mais rápida de carregamento de página.
- O usuário recebe o conteúdo solicitado e pode visualizar a página HTML, imagem ou currículo.
- O CloudWatch realiza monitoramento básico dos recursos para informar caso algo fora no padrão possa acontecer.

> O Amazon Route 53 desempenha um papel fundamental na rota do tráfego do usuário para o CloudFront. Ele gerencia o DNS do domínio, garantindo que as solicitações sejam direcionadas corretamente para o CloudFront. Isso permite que o CloudFront atue como uma camada de cache global, entregando o conteúdo com baixa latência a partir do ponto de presença mais próximo do usuário.
