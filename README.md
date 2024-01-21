# INTRODUÇÃO AO NMAP COM METASPLOITABLE
  >Primeiramente, seria interessante possuir armazenamento e processamento consideráveis.

**METASPLOITABLE** <br />
O Metasploitable é uma máquina virtual com vulnerabilidades intencionais para serem exploradas, muito utilizada para estudos e práticas. 
Você pode baixá-la no site da SourceForge.net e colocá-la dentro da VirtualBox. Também será necessária uma distribuição Linux (por hora pode ser qual você desejar), mas eu recomendo o Kali Linux nessa ocasião. <br />

_Login e senha utilizados no Metasploitable: msfadmin_

**RESUMINDO, PRECISAREMOS DE:** <br />
VirtualBox com Metasploitable   <br />
VirtualBox com Kali Linux 

**FERRAMENTA NMAP** <br />
Nmap é a abreviação de Network Mapper (em português, "mapeador de rede"). É uma ferramenta open source do Linux (sua interface gráfica é a ZeNmap), usada para efetuar a varredura (scan) de endereços IP e portas em uma rede e detectar aplicações instaladas.

Muito utilizada por administradores de rede para identificar facilmente os hosts conectados, qual sistema operacional dos dispositivos, suas versões, portas abertas e descoberta de malware, scripts do Nmap Script Engine, entre muitos outros. 

**CONHECIMENTOS BÁSICOS** <br />
A análise pode ser feita de 3 tipos: 
 - Por IP: nmap 127.0.0.1
 - Por um domínio: nmap github.com
 - Pela rede: nmap 192.168.0.0/24
   
**COMANDOS:** <br />
Execute o comando _-ifconfig_ na sua máquina Metasploitable para pegar o IP (já que estamos em ambiente de teste e.e) <br />
Em seguida, você vai usar o Kali Linux para fazer as varreduras, como se o metasploitable fosse outra máquina vulnerável da qual queremos pegar informações.

  - nmap -v 192.168.0.56.0/24 – Usado para verificar os todos hosts dentro dessa rede, do 0 ao 255. Dessa forma, aparecerá algumas portas abertas de um determinado IP (host) e os serviços. 
  - nmap -v -sn 192.168.0.110 - Apenas para saber se o host está ativo 
  - nmap -v -sn 192.168.56.100-200 - Também é possível limitar pelo intervalo de IP, fazendo a varredura entre os hosts 100 e 200 apenas. 
  - nmap -v -sn 192.168.56.100-110 | grep 105 > varredura.txt – Basicamente, é o comando acima, mas deixamos filtrado o host 105 e depois salvamos toda varredura no arquivo de texto “varredura.txt”. 
O comando grep é como uma mão na roda, permite que você encontre facilmente uma informação entre várias outras.

>Agora você sabe o básico sobre ambiente de testes e Nmap, utilize toda sua criatividade para aprimorar seu conhecimento.<br />

_“A imaginação é mais importante que o conhecimento. O conhecimento é limitado, enquanto a imaginação abraça o mundo inteiro, estimulando o progresso, e dando origem à evolução” Albert Einstein_
> [!IMPORTANT]
> Esse conteúdo foi criado para fins didáticos. A utilização é por sua conta e risco.
