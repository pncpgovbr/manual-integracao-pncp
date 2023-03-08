3.1. Endereços de Acesso

A invocação dos serviços será realizada através das  URLs citadas abaixo, conforme requisitos de segurança detalhados na seção seguinte. 

Ambiente de Homologação Externa:

Portal: https://treina.pncp.gov.br 
Documentação Técnica (Serviços): https://treina.pncp.gov.br/api/pncp/swagger-ui/index.html?configUrl=/pncp-api/v3/api-docs/swagger-config 
Serviços (${BASE_URL}): https://treina.pncp.gov.br/api/pncp 

Ambiente de Produção:
Portal: https://pncp.gov.br 
Documentação Técnica (Serviços): https://pncp.gov.br/api/pncp/swagger-ui/index.html?configUrl=/pncp-api/v3/api-docs/swagger-config 
Serviços (${BASE_URL}): https://pncp.gov.br/api/pncp 

Nota: ${BASE_URL} será utilizada nos exemplos de requisições citados neste documento. É a URL base para acesso aos serviços disponíveis no PNCP. 


3.2. Autenticação/Autorização

O acesso ao Portal de consultas é público. Já as APIs de manutenção (serviços de inserção, retificação ou exclusão de dados) requerem autenticação/autorização.
As plataformas digitais que fornecerão os dados para publicação, representando os órgãos públicos e entidades, deverão realizar credenciamento junto ao Ministério da Gestão e da Inovação em Serviços Públicos, quando receberão login e senha para acesso. A plataforma digital é responsável pela guarda e confidencialidade das suas credenciais.
Qualquer usuário pode alterar sua própria senha, seguindo as seguintes regras:
A senha deve conter no mínimo 16 caracteres válidos e no máximo 64 caracteres.
A senha não pode conter o login do usuário.
A senha não pode conter um nome de usuário.
A senha não pode conter nomes do e-mail do usuário.
A senha não pode conter sequências de 3 ou mais do mesmo caractere.
A senha não pode conter sequências de 4 ou mais caracteres crescentes.
A senha não pode conter sequências de 4 ou mais caracteres decrescentes.
Caracteres “brancos” no início e fim da senha serão desprezados (a senha pode conter caracteres “brancos” entre outros caracteres).

A plataforma usuária deverá se autenticar com login e senha para obter um JSON Web Token (JWT). Utilizando esse token, a plataforma poderá acessar os serviços disponíveis, até a expiração do mesmo (prazo de 1 hora a partir da sua geração). Um único token é necessário para a plataforma durante sua validade e, uma vez expirado, uma nova autenticação será necessária para obter um novo token.
A API de login (POST https://pncp.gov.br/api/pncp/v1/usuarios/login) retorna o JWT no cabeçalho (header) da resposta HTTP, especificamente no campo “Authorization”, após o texto “Bearer”. As requisições a APIs de manutenção de dados no PNCP requerem esse campo de cabeçalho idêntico para autenticação e autorização.
Quando da primeira publicação do sistema, a associação entre usuários e seus órgãos/entidades autorizados estará sendo feita pelo próprio usuário. Ou seja, a plataforma deverá informar ao sistema quais CNPJs ela representa e assim estará autorizada a enviar dados em nome destes. O sistema confiará na plataforma e ela será juridicamente responsável por quaisquer equívocos, intencionais ou acidentais.
