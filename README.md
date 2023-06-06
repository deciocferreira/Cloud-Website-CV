# AWS Cloud Project <image src="https://user-images.githubusercontent.com/12403699/234434276-e7cdcab8-c594-47a6-8862-7645e5740a2c.png" width="80" height="50">  
  
## Proposta de arquitetura para hospedagem de um WebSite na AWS.
  
## Tecnologias utilizadas  
  
- Amazon CloudFront

- Amazon Route 53
  
- Amazon S3 
  
- Amazon CloudWatch
  
- Amazon Shield Standard  
  
- Amazon Certificate Manager  
  
## Objetivo

Desenvolvimento de um website (html, css, imagens) contendo os currículos do grupo e a implantação de um ou mais serviços na nuvem AWS, com rede de entrega de conteúdo, com baixa latência, com segurança, e armazenamento durável, para atender a demanda de 11 milhões de requisições por mês.  
  
## Arquitetura

<image src="https://github.com/deciocferreira/Cloud-Website-CV/assets/12403699/b5a2b33c-0863-42c5-9add-e58b99119e0f" width="900" height="700">
             
## Fluxo da arquitetura
-	O usuário faz uma solicitação para acessar um website estático que contém os currículos.
-	O Amazon Route 53 faz o trabalho de DNS garantindo o direcionamento correto do tráfego e registro do domínio personalizado grupo3aws.xyz.
-	Depois, o tráfego é direcionado para o Amazon CloudFront, que atua como uma CDN (Content Delivery Network) e vai no Amazon S3 para acessar o conteúdo para retornar para o usuário.
-	O ACM gerencia um certificado gratuito que importamos para ser usado pelo Cloudfront.
-	Além disso, o CloudWatch, realiza um monitoramento básico dos recursos para informar caso algo fora do padrão ocorra. Ele está presente para nos fornecer insights valiosos e nos alertar caso surjam problemas.
-	Na segurança, o Amazon Shield Standard é habilitado por padrão quando configuramos o CloudFront e Route53, assim garantindo análise de ameaças e proteção de ataques DDOS, já que a aplicação é acessada globalmente.

## Proposta
  
Custo mensal: US$ 2,80

Custo anual: US$ 33,60

Calculadora: https://calculator.aws/#/estimate?id=0115ff284c737438bcc7a28e23e8ac8d7aa8ff66

Custo de domínio personalizado: R$10,94  
