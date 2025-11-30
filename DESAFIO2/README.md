Simulando um Malware de Captura de Dados Simples em Python e Aprendendo a se Proteger


O objetivo deste exercício é simular, de forma segura e controlada, o comportamento básico de um ransomware, sem causar dano real e sem utilizar técnicas ilegais. A simulação permite compreender a lógica de ataque e desenvolver habilidades de prevenção.

Exercício elaborado com auxílio do ChatGPT e realizado sem inclusão de código, em virtude dos riscos de compartilhamento de informações que podem ser utilizadas para fins ilegais.

“Ransomware Simulado” (sem dano real)

1.	Para a criação de um ransomware simulado, o primeiro passo é criar os arquivos de teste controlado, abrindo uma pasta e inserindo arquivos (cópia de arquivos reais ou fictícios) nela.

2. Criar o script para criptografar conteúdo da pasta. O código deve seguir a seguinte lógica:
	a) Abrir arquivo original
	b) Ler conteúdo
	c) Transformar conteúdo: inverter ordem dos caracteres. A inversão dos caracteres é uma transformação totalmente reversível, permitindo simular a ideia de “arquivo inacessível” sem empregar criptografia real nem riscos de perda de dados.
	d) Salvar em um novo arquivo com a extensão ".simlock"
	e) Apagar somente o arquivo de teste original 
	f) Importante registrar no código onde salvar o arquivo criptografado e que ele não deve ser incluído nos arquivos originais atingidos pelo ransomware.
	g) O código deve incluir apenas os dados da pasta criada para fins de simulação, sob risco de prática ilegal. Isso garante que nenhum arquivo pessoal ou do sistema seja modificado, preservando a ética e a segurança do ambiente.

3. Criando o Script de “descriptografia” 
	a) Criar um código dentro da pasta de simulação, que leia o conteúdo de cada arquivo .simlock
	b) Reverter a transformação (inverter string novamente)
	c) Grave em arquivo normal ".txt" ou nome original

4. Na criação da mensagem de resgate do Ransomware é comum utilizar as técnicas de engenharia social, explorando: senso de urgência, medo, incerteza técnica do usuário e autoridade. Por exemplo: 

ATENÇÃO!!!!!
Seus arquivos foram "SEQUESTRADOS".
Se quiser recuperar seus dados, siga atentamente as instruções:

1. Responda ao e-mail informado.
2. Não tente restaurar os arquivos por conta própria, qualquer tentativa de violar o código irá resultar na destruição dos seus dados e você nunca mais irá recuperá-los.
3. Você tem 2 horas a partir do recebimento desse e-mail para entrar em contato para negociar. A cada hora a mais, irei corromper uma parte do seu disco rígido.

Pontos que mostram engenharia social:
a) Urgência ("tempo limitado")
b) Ameaça de perda - não recuperar os dados (risco presente) e corromper o disco rígido (risco futuro)
c) Impedir ação independente ("não tente por conta própria")
d) Autoridade falsa ("siga atentamente")

Este exercício evidencia como ataques de ransomware combinam aspectos técnicos e psicológicos. Ao compreender a lógica de operação e os gatilhos de engenharia social presentes nas mensagens de resgate, torna-se mais fácil identificar sinais de ataque e adotar medidas preventivas eficazes.


“Keylogger Simulado” (seguro e ético)

1.	Criar uma função para a captura de dados digitados pelo usuário e salvá-los em um arquivo, com a seguinte estrutura lógica.
	texto_digitado = input("Digite algo para o teste: ")
	abrir arquivo "registro_teclas.txt"
	registrar a data e o texto digitado

2. Para que o código não seja visto pelo usuário é comum utilizar elementos de furtividade. Para tanto, o script criado pode: 
	a) mudar o nome do arquivo de registro para algo inocente (“log_sistema_01.txt”)
	b) usar uma pasta pouco acessada do sistema (como /temp/ do próprio laboratório)
	c) reduzir mensagens na tela (funcionando “em silêncio”)

3. Dependendo do controle que o atacante possui na máquina atacada é interessante que ele faça a exfiltração dos dados, mediante envio dos dados capturados por e-mail ou usando uma backdoor.

Como evitar ou mitigar os riscos desses ataques?


1) Backup regular e isolado - Backups offline impedem que ransomware ataque a cópia.

2) Atualizações constantes (patching) - Muitas infecções exploram vulnerabilidades já corrigidas.

3) Não abrir anexos suspeitos - Phishing ainda é o método nº 1 de entrada.

4) Uso de antivírus/EDR - Detecta comportamentos incomuns como modificação massiva de arquivos, hooks de teclado e comunicação não usual

5) Privilégios mínimos - Contas sem permissão de administrador reduzem impacto.

6) Monitoramento de logs - Anomalias de escrita massiva ou criação de arquivos estranhos podem alertar cedo.

7) Uso de duplo fator de autenticação - No caso keylogger, usar o duplo fator de autenticação, reduz o risco de acesso com  as senhas obtidas, pois sem o segundo item do fator ("o que você é" ou "o que você tem"), o atacante não consegue efetivar o ataque apenas com a senha.

8) Conscientização e treinamento - Usuários são o alvo principal; entender engenharia social reduz riscos.
