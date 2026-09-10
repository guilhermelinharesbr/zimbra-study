# zmcontrol


### Sumário

- [ZMCONTROL](#zmcontrol)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [zmcontrol -h / zmcontrol --help](#zmcontrol--h--zmcontrol---help)
- [zmcontrol -H](#zmcontrol--h)
- [zmcontrol -v](#zmcontrol--v)
- [zmcontrol status](#zmcontrol-status)
- [zmcontrol restart](#zmcontrol-restart)
- [zmcontrol start](#zmcontrol-start)
- [zmcontrol startup](#zmcontrol-startup)
- [zmcontrol stop](#zmcontrol-stop)
- [zmcontrol shutdown](#zmcontrol-shutdown)

---

#### ZMCONTROL

Gerencia os serviços (ligar, desligar, status).

---

#### Fonte de Pesquisa

[zmcontrol wiki](https://wiki.zimbra.com/wiki/Zmcontrol "Comando zmcontrol na Wiki do Zimbra")

---

#### zmcontrol -h / zmcontrol --help

Mostra as opções de ajuda. O `zmcontrol --help` mostra um pouco mais de ìnformações que o `zmcontrol -h`.

Ex:
```bash
su zimbra
zmcontrol --help
ou 
zmcontrol -h
```

---

#### zmcontrol -H

Usado para deixar mais visível em que servidor o adminstrador está trabalhando. A opção `-H` é para indicar o Host name(default is localhost). 

Ex:
```bash
zmcontrol -H mail.empresa.com.br status
#Este comando acima seria o mesmo que rodar o comando abaixo
zmcontrol status
```

---

#### zmcontrol -v


Exibe a versão exata do Zimbra que está instalada no servidor.


Ex:
```bash
su zimbra
zmcontrol -v
```

Saída:
_Release 8.8.15_GA_3869.RHEL7_64_20190917004220 RHEL7_64 FOSS edition, Patch 8.8.15_P45._

A partir dessa saída, você consegue identificar informações cruciais:

**8.8.15_GA**: A versão principal do Zimbra (Geralmente **GA** significa General Availability, ou versão estável).
**RHEL7_64**: O sistema operacional para o qual essa versão foi compilada (neste exemplo, Red Hat Enterprise Linux 7 de 64 bits).
**FOSS edition** ou **Network edition**: O tipo de licença. FOSS é a versão gratuita/código aberto (**F**ree and **O**pen **S**ource **S**oftware), enquanto Network indica a versão comercial paga.

---

#### zmcontrol status

Verifica o estado de execução de todos os serviços do Zimbra no servidor.

Ex:
```bash
su zimbra
zmcontrol status
```

---

#### zmcontrol restart

Reinicia completamente o Zimbra. 
Na prática, ele faz o trabalho de dois comandos de uma vez só: primeiro ele para todos os serviços do Zimbra que estão rodando e, em seguida, inicia cada um deles novamente.

Ex:
```bash
su zimbra
zmcontrol restart
```

---

#### zmcontrol start

Inicia todos os serviços do Zimbra que estão parados.

Ex:
```bash
su zimbra
zmcontrol start
```

---

#### zmcontrol startup

Inicia todos os serviços do Zimbra que estão parados.

Ex:
```bash
su zimbra
zmcontrol startup
```

---

#### zmcontrol stop

Para todos os serviços do Zimbra.

Ex:
```bash
su zimbra
zmcontrol stop
```

---

#### zmcontrol shutdown

Para todos os serviços do Zimbra.

Ex:
```bash
su zimbra
zmcontrol shutdown
```

---
