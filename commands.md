# Zimbra commands


### Sumário

- [ZMPROV](#zmprov)
- [Fonte de Pesquisa zmprov](#fonte-de-pesquisa-zmprov)
- [zmprov gad / zmprov getAllDomains](#zmprov-gad--zmprov-getalldomains)
- [zmprov cd / zmprov createDomain](#zmprov-cd--zmprov-createdomain)
- [zmprov dd / zmprov deleteDomain](#zmprov-dd--zmprov-deletedomain)
- [zmprov gaa / zmprov getAllAccounts](#zmprov-gaa--zmprov-getallaccounts)
- [zmprov ca / zmprov createAccount](#zmprov-ca--zmprov-createaccount)
- [zmprov da / zmprov deleteAccount](#zmprov-da--zmprov-deleteaccount)
- [zmprov ma / zmprov modifyAccount](#zmprov-ma--zmprov-modifyaccount)
- [zmprov gsi / zmprov getShareInfo](#zmprov-gsi--zmprov-getshareinfo)
- [zmprov gadl / zmprov getAlldistributionLists](#zmprov-gadl--zmprov-getalldistributionlists)
- []()
- []()
- []()
- []()

---

#### ZMPROV

O zmprov (Zimbra **Prov**isioning CLI) é a ferramenta de linha de comando mais poderosa e utilizada no Zimbra. Gerencia as contas, senhas, domínios, listas de discussão e configurações internas.

---

#### Fonte de Pesquisa zmprov

[Zmprov Wiki](https://wiki.zimbra.com/wiki/Zmprov "Comando zmprov na Wiki do Zimbra")

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

Ex:
```bash
zmprov gsi financeiro@dominio.com.br
ou
zmprov getShareInfo financeiro@dominio.com.br
```

---

#### zmprov gadl / zmprov getAlldistributionLists

Exibe em todas as listas de distribuição.

Ex:
```bash
zmprov gadl dominio.com.br
ou
zmprov getAlldistributionLists dominio.com.br
```

---
