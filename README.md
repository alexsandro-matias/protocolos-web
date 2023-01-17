Como funciona um protocolo – http – hyperText Transfer Protocol – intermédio entre o cliente e o servidor 
•	Definidos pelo RFCs 1945 e 2116
•	Browser – implementa o cliente http – pode não ser utilizado o browser para essa comunicação.
•	Servidor – host objetos
•	 web – hospedar os recursos que o cliente estará solicitando
cliente
•	 Requisitar os recursos – request – objetos web
Serviror 
Responde as mensagens solicitadas – response – protocolo http 
Responsabilidades definidas – o que será enviado de acordo com a requisição que recebeu ou seja não guarda estado do cliente. Assim se o cliente fazer a mesma solicitação mais de uma vez, o servidor irá responder mais de uma vez – não guarda estado (redundância) - stateless 

Arquitetura cliente servidor 



Conexão (comunicação persistente) X não persistente – persistente somente é encerrada a partir de uma ação. Não persistente depois da resposta a conexão é fechada.

Get – solicitar algum conteúdo ao servidor -> browser irá enviar uma requisição com método get para o site qualquer -> o servidor da amazon vai procurar as informações para satisfazer a requisição -> responde com a mensagem http response 

Post – submissão de uma requisição e o servidor é obrigado a tratar aquele conteúdo -> enviando uma requisição http -> um envio de um cadastro -> cliente vai enviar uma mensagem request com o método post -> servidor vai atualizar o Banco de Dados com as informações que foram passadas -> servidor enviar uma resposta dizendo que foi processada de forma correta

O formato de envio ou mapeamento (http Entity Body) desses dados podem ser feito xml ou json. Os objetivos são armazenar, transmitir e reconstruir as informações no percursos dos dados. Essa determinação do tipo é através do content-type. Já para o recebimento é Accept o formato se será json ou xml.
Esses arquivos tem a função de serialização dos dados para haja uma comunicação entre as partes, sendo o xml se tornando interessante para metadados.
O json foi concebido na ideia do Javascript sendo light weight – legibilidade e independete da linguagem de programação com estrutura de chave e valor – dicionário

Comum entre eles – auto-descritivos, hierárquicos, independentes de linguagem de programação, vasta utilização

Diferenças 
Xml – tags, mais complexo, ainda é usado para alguma aplicações 
Json – chave valor, sucinto, vetores 

para selcionar quais das duas depende da tecnologia utilizada – legado xml – aplicação mais leves json – maior complexidade metadados xml 

http 1.1
protocolo – tcp – tramission control protocol – protocolo na camada de transporte – essa comunicação de três vias – o cliente enviou para o servidor – ok – inicia-se a conexão e envia para o cliente responde ok – essa comunicação persistente vai existir 

quando é uma requisição para executar outra requisição somente quando obtiver a resposta da primeira requisição. Isso é problema. O browsers para contornar essa situação eles permitem que o cliente façam 6 requisições http simultâneas, ou seja se não houver mais 6 objetos o mesmo cliente pode realizar em paralelo.
Caso haja a necessidade do cliente permanecer conectado e é possível manter essa conexão aberta e dentro desta conexão enviando todas as requicoes necessárias, então haverá HOL – Head of Line Blocking – uma vez que facah a requisição não é possível fazer nem outra até que seja encerrada a anterior até receber a resposta. 
Repetição dos dados – em toda a requisição é utilizado o cabeçalho, isso vai causar uma inundação da rede, muitas vezes, esse cabeçalho é repetitivo. Enviando pacotes maiores que precisaria – o http por cima do tcp 

response
Estrutura – request line – método + 
Os request servem para enviar requisições e a grande maioria são o método get 


Exemplo:
1. Get:/somedir/page.html/HTTP/1.1 (Request Line) (Head Line)
2. Host: www.someschool.edu (Head Line)
3. Connection:close (Head Line)
4. User-agent: Mozilla/5.0 (Head Line)
5. Accept-language:fr (Head Line).

Detalhando essas etapas:

1. Request Line com o método ``Get`` solicitando uma página específica com a versão 1.1 do protocolo.
2. Host da aplicação, se estivesse sendo executada na máquina seria localhost ou endereço padrão para localhost.
3. Connection close significando não persistente.
4. User-agent é o agente que está realizando a requisição, ou seja, a tecnologia aplicada por ela. Nela poderia um por curl, navegador ou aplicação Java.
5.  Accept-language é o idioma de preferência do cliente.

Principais métodos 
- Get - Solicita um recurso do servidor
- Head - Get sem corpo de resposta - apenas o cabecalho 
- post - Submete uma entidade a um recurso - o servidor é obrigado a tratar aquele comando - definição de formato ou parâmetros para segurança 
- Put - Substituição parcial dos recursos pelos dados da requisição
- Delete - remoção de um recurso 
- Trace - Chamada de loop-back a um determinado recurso;
- Option - opções de comunicação com recurso - 
- Connect - Tunelamento identificado pelo recurso
- Patch - Modificação parcial - RFC 5789


Métodos seguros – método que tando executado não alteram o resultado do servidor, ou seja, apenas modo de leitura – idempotentes – sempre o mesmo resultado – get ou post ou option – 
Um métodos seguro podem causa


## HTTP response
- Versão do protocolo 
- Status code
- Status da mensagem

#### Códigos 
- 200 OK - request bem sucessida e objetivo enviado ao objetivo; - 
- 301 moved permanently - Objeto realocado nova URL no campo Location - execucao de um url ela foi realocada 
- 400 Bad request - reposta genérica - servidor não entendeu a mensagem 
- 404 Not found - documento solicitado é inexistente
- 505 http version not supported - versao do protocolo não suportada pelo servidor 


#### Classificação dos códigos -RFC 2616
- Information response (100-199)
- Succesfull response (200-299)
- Redirection response (300-399)
- Client error response (400-499)
- server error response (500-599)


#### Web Distributed Authoring and Versioning
- 102 - Processing 
- 207 - Multi-status 
- 208 - Already reported 
- 422 - Unprocessable Entity
- 423 - Locked
- 422 - Failed Dependency


>> WebDAv, CalDav, CardDAV










