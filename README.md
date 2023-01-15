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

Métodos seguros – método que tando executado não alteram o resultado do servidor, ou seja, apenas modo de leitura – idempotentes – sempre o mesmo resultado – get ou post ou option – 
Um métodos seguro podem causa






