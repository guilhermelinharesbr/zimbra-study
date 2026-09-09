# Zimbra commands


### Sumário
- [ZMCONTROL](#zmcontrol)
- [zmcontrol --help / zmcontrol -h](#zmcontrol---help--zmcontrol--h)
- [zmcontrol -v](#zmcontrol--v)
- [zmcontrol status](#zmcontrol-status)
- [zmcontrol restart](#zmcontrol-restart)
- [zmcontrol start](#zmcontrol-start)
- [zmcontrol stop](#zmcontrol-stop)
- [ZMPROV](#zmprov)
- [zmprov gad / zmprov getAllDomains](#zmprov-gad--zmprov-getalldomains)
- [zmprov cd / zmprov createDomain](#zmprov-cd--zmprov-createdomain)
- [zmprov dd / zmprov deleteDomain](#zmprov-dd--zmprov-deletedomain)
- [zmprov gaa / zmprov getAllAccounts](#zmprov-gaa--zmprov-getallaccounts)
- [zmprov ca / zmprov createAccount](#zmprov-ca--zmprov-createaccount)
- [zmprov da / zmprov deleteAccount](#zmprov-da--zmprov-deleteaccount)
- [zmprov ma / zmprov modifyAccount](#zmprov-ma--zmprov-modifyaccount)
- [zmprov gsi / zmprov getShareInfo](#zmprov-gsi--zmprov-getshareinfo)
- []()



---

#### ZMCONTROL

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

#### zmcontrol stop

Para todos os serviços do Zimbra.

Ex:
```bash
su zimbra
zmcontrol stop
```

---

#### ZMPROV

O zmprov (Zimbra **Prov**isioning CLI) é a ferramenta de linha de comando mais poderosa e utilizada no Zimbra. Gerencia as contas, senhas, domínios, listas de discussão e configurações internas.

---

#### zmprov gad / zmprov getAllDomains

**gad** -> get all domains.

Ex:
```bash
zmprov gad
ou 
zmprov getAllDomains
```

---

#### zmprov cd / zmprov createDomain

**cd** -> create domain.

Ex:
```bash
zmprov cd dominio.com.br
ou 
zmprov createDomain dominio.com.br
```

---

#### zmprov dd / zmprov deleteDomain

**dd** -> delete domain.

Ex:
```bash
zmprov dd dominio.com.br
ou 
zmprov deleteDomain dominio.com.br
```

---

#### zmprov gaa / zmprov getAllAccounts

**gaa** -> get all account.

Imprime na tela todas as contas independente do domínio:

```bash
zmprov -l gaa
ou
zmprov -l getAllAccounts
```

Imprime na tela todas as contas do domínio dominio.com.br:

```bash
zmprov -l gaa dominio.com.br
```

Obs: A opção **-l**: Abreviação de _LDAP_. Este parâmetro é um truque de desempenho crucial. Ele diz ao Zimbra para ler os dados diretamente do serviço de diretório local (LDAP) em vez de fazer uma requisição SOAP completa pelo servidor web. Isso torna a resposta do comando muito mais rápida, especialmente se o servidor tiver milhares de contas.

Exibe o total de contas deste domínio:

```bash
zmprov -l gaa dominio.com.br | wc -l
```

---

#### zmprov ca / zmprov createAccount

**ca** -> create account.

Cria a conta de email para o usuário Guilherme e já define a senha dele:
```bash
zmprov ca guilherme.linhares@dominio.com.br SuaSenhaSeguraAqui
```

Cria a conta e já define nome, sobrenome e nome de exibição:
```bash
zmprov ca guilherme.linhares@dominio.com.br @123456 givenName "Guilherme" sn "Linhares" displayName "Guilherme Linhares"
```

---

#### zmprov da / zmprov deleteAccount

Deleta uma conta de email:
```bash
zmprov da guilherme.linhares@dominio.com.br
```

---

#### zmprov ma / zmprov modifyAccount

Bloqueia uma conta:
```bash
zmprov ma guilherme.linhares@dominio.com.br zimbraAccountStatus locked
```

Desbloqueia uma conta:
```bash
zmprov ma guilherme.linhares@dominio.com.br zimbraAccountStatus active
```

---

#### zmprov gsi / zmprov getShareInfo

Esse comando retorna informações sobre compartilhamentos publicados, quando o proprietário é especificado, o servidor percorre a mailbox dele pra descobrir todos os compartilhamentos aplicáveis. A saída inclui todos os campos importantes: id do dono, e-mail do dono, id da pasta, caminho completo da pasta, tipo de visualização, direitos concedidos, tipo de concessão (grantee), id e nome do concessionário.

Desbloqueia uma conta:
```bash
zmprov gsi financeiro@dominio.com.br
ou
zmprov getShareInfo financeiro@dominio.com.br
```

---
