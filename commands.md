# Zimbra


### Sumário
- [zmcontrol](#zmcontrol)
- [zmcontrol --help / zmcontrol -h](#zmcontrol---help--zmcontrol--h)
- [zmcontrol -v](#zmcontrol--v)
- []()
- []()

---

#### zmcontrol

Gerencia os serviços (ligar, desligar, status).

---

#### zmcontrol --help / zmcontrol -h

Mostra as opções de ajuda.

Ex:
```bash
su zimbra
zmcontrol --help
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