# SSL e Certificados Digitais

## Nome
Vinicius Calefo Assarice

## Ambiente
- Sistema Operacional: Windows com WSL (Windows Subsystem for Linux)
- Distribuição Linux: Ubuntu 13
- OpenSSL 3.x
- Python 3.x
- Git

## IP
172.17.219.119

## Dificuldades

### Exercício 6 – Falha na transferência via SCP
A principal dificuldade encontrada foi no exercício 6. O ambiente WSL
apresentou problemas de autenticação SSH que impediram a execução do SCP.
Mesmo após resetar a senha do usuário comum e do root múltiplas vezes,
a autenticação continuava falhando, impossibilitando a transferência do
certificado para outra máquina.

Esse problema é uma limitação conhecida do WSL: por padrão, o serviço SSH
não vem habilitado e o root pode ter autenticação por senha desativada
nas configurações do sshd. Em um ambiente com duas VMs reais ou duas
máquinas físicas, o exercício seria realizado sem essa dificuldade.

### Outras dificuldades
- Configurar o prompt personalizado com o nome de usuário
- Promover o usuário para superusuário (sudo) antes de iniciar
- Entender a diferença entre HTTP e HTTPS na prática

## Conclusão
Esta atividade permitiu compreender na prática todo o ciclo de vida de um
certificado digital SSL: desde a geração da chave privada RSA, passando pela
criação do CSR, emissão do certificado autoassinado no padrão X.509,
transferência segura via SCP (exercício não concluído por limitação do
ambiente WSL), até a configuração de um servidor HTTPS real.

Foi possível entender na prática por que navegadores exibem alertas para
certificados autoassinados: a ausência de uma Autoridade Certificadora (CA)
reconhecida quebra a cadeia de confiança (Chain of Trust), mesmo que a
criptografia esteja funcionando corretamente.

O exercício 7 foi realizado de forma avançada, implementando TLS real com
Python ao invés do servidor HTTP simples proposto, o que proporcionou um
entendimento mais profundo do handshake SSL e do funcionamento da
criptografia em uma conexão HTTPS.