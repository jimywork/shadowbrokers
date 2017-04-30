# Eternal Blue CIA Tools
Eternalblue é apenas uma das ferramentas hackers para Windows que foi vazada para o público na sexta-feira 14 de abril pela Shadow Brokers. A 'série' eterna cobre muito mais explorações como Eternalromance, Eternalchampion e Eternalsynergy, todas com sistemas operacionais recentes do Windows. Para configurar e executar os exploits contra alvos vulneráveis existe uma estrutura de exploit incluída chamada Fuzzbunch. O Fuzzbunch é desenvolvido em Python 2.6 e tem muitas semelhanças com o framework Metasploit. Nas etapas a seguir, vamos instalar os pré-requisitos, configurar o Fuzzbunch e aprender como executar o Eternalblue.

## Instalando pré-requisitos na máquina Windows 7

Na máquina de ataque do Windows 7 precisamos instalar o Python 2.6 eo PyWin32 v212. Os arquivos de instalação podem ser baixados aqui:

Python 2.6: https://www.python.org/download/releases/2.6/

PyWin32 v212: https://sourceforge.net/projects/pywin32/files/pywin32/Build%20212/

Siga as etapas de instalação para o Python primeiro e depois para o PyWin32. Certifique-se de que instala o PyWin32 como administrador, caso contrário poderá obter erros ao executar o script pós-instalação. Se você precisa executar o script de pós-instalação novamente, ele está localizado no seguinte diretório:

<pre>
<code>C:\Python26\Scripts</code>
</pre>

## Configurando o Fuzzbunch

O próximo passo é baixar o arquivo Shadow Brokers e descompactá-lo para a área de trabalho. Quando você baixou o arquivo do Github você tem que criar uma nova pasta chamada 'listeningspost' no diretório do Windows que contém o arquivo fb.py (Fuzzbunch).
<pre>
<code>fbctf@fbctf:~$ git clone https://github.com/fbctf/shadowbrokers.git</code>
</pre>
<br>
<pre>
<code>
"""
Plugin directories
"""
PAYLOAD_DIR = os.path.join(FB_DIR, "payloads")
EXPLOIT_DIR = os.path.join(FB_DIR, "exploits")
TOUCH_DIR   = os.path.join(FB_DIR, "touches")
IMPLANT_DIR = os.path.join(FB_DIR, "implants")
# LP_DIR      = os.path.join(FB_DIR, "listeningposts")
EDE_DIR     = os.path.join(FB_DIR, "ede-exploits")
TRIGGER_DIR = os.path.join(FB_DIR, "triggers")
SPECIAL_DIR = os.path.join(FB_DIR, "specials")
</code>
</pre>
Finalmente, edite o arquivo de configuração Fuzzbunch denominado fuzzbunch.xml e defina os parâmetros ResourcesDir e LogDir apropriados:
<code>

    <t:parameter name="ResourcesDir"
                 description="Absolute path of the Resources Directory"
                 type="String"
                 default="D:\DSZOPSDISK\Resources"/>

</code>
<code>

    <t:parameter name="LogDir"
                 description="Absolute path of an Initial Log Directory"
                 type="String"
                 default="C:\shadowbrokers\fuzzbunch\logs"/>
</code>

Altere os parâmetros de localização do log e dos recursos do Fuzzbunch.
Agora execute o debbuger
<code>
</code>

Agora podemos iniciar o Fuzzbunch executando o arquivo fb.py a partir da linha de comando e ele deve ser executado sem erros:
<pre>
<code>
  fbctf@fbctf:~$ python fb.py
</code>
</pre>
