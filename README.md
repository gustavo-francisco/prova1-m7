# prova1-m7

Em ambos os dockerfile eu inicio com os frameworks que os códigos utilizam. Defino também um diretório de trabalho.
No Dockerfile do backend eu uso o comando COPY para trazer o arquivo requirements e logo em seguida uso o RUN para instalá-lo na imagem antes de tudo. após isso, copio tudo no diretório de trabalho e depois defino a porta que vai escutar essa imagem através do comando EXPOSE. Por último, uso o CMD, que basicamente é o comando que o terminal fará automaticamente para rodar o arquivo.
No Dockerfile do frontend eu uso o COPY para copiar o package.json (toda minha aplicação node) para minha imagem. O pulo do gato está no *, pois traz também o package-lock.json. Uso o RUN para instalar a aplicação na imagem e depois copio tudo do diretório atual para a imagem. Defino a porta que vai escutar e no final rodo o node server.js para rodar a aplicação.
No docker-compose defino os serviços do meu arquivo (o back e o front) falo pra ele buildar através dos dockerfile que defini para cada um. também defino as portas que vão escutar, tanto da minha máquina quanto da imagem. No caso, são as mesmas.
