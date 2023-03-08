1. Objetivo

Este documento contempla as orientações para realizar a integração de sistemas externos com as API REST do PNCP (Portal Nacional de Contratações Públicas).

2. Protocolo de Comunicação

O protocolo de comunicação utilizado é o REST - Representational State Transfer/ HTTP 1.1 e os dados trafegados utilizam a notação JSON - JavaScript Object Notation. Informações enviadas via o header de uma requisição devem estar de acordo com o charset ISO-8859-1, e arquivos enviados para o Portal devem ser codificados em charset UTF-8, quando aplicável (por exemplo, em arquivos .txt e em arquivos JSON, quando utilizados como payload de uma requisição).
