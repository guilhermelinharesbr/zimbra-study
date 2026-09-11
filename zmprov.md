# zmprov


### Sumário

- [Definição](#definição)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [Opções Gerais](#opções-gerais)
- [zmprov --help / zmprov -h](#zmprov---help--zmprov--h)
- [Comandos de provisionamento de Domínio](#comandos-de-provisionamento-de-domínio)
- [zmprov countAccount / zmprov cta](#zmprov-countaccount--zmprov-cta)
- [zmprov createDomain / zmprov cd](#zmprov-createdomain--zmprov-cd)
- [zmprov deleteDomain / zmprov dd](#zmprov-deletedomain--zmprov-dd)
- [zmprov getDomainInfo / zmprov gdi](#zmprov-getdomaininfo--zmprov-gdi)
- [zmprov gad / zmprov getAllDomains](#zmprov-gad--zmprov-getalldomains)
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

### Definição

O zmprov (Zimbra **Prov**isioning CLI) é a ferramenta de linha de comando mais poderosa e utilizada no Zimbra. Gerencia as contas, senhas, domínios, listas de discussão e configurações internas.

---

### Fonte de Pesquisa

[Zmprov Wiki](https://wiki.zimbra.com/wiki/Zmprov "Comando zmprov na Wiki do Zimbra")

---

### Opções Gerais

As opções gerais do comando zmprov serão mostradas mais abaixo neste artigo.

---

#### zmprov --help / zmprov -h

Mostra o meu de ajuda do comando zmprov.

Ex:
```bash
zmprov --help
ou 
zmprov -h
```

---

### Comandos de provisionamento de Domínio

Comandos que são usados para criação, configuração, etc dos domínios no Zimbra. 

---

#### zmprov getDomain

Para descobrir o ID do domínio:
```bash
zmprov gd empresa.com.br zimbraId
```

---

#### zmprov countAccount / zmprov cta

Serve pra contar quantas contas existem em um domínio, agrupadas por Classe de Serviço (COS), útil principalmente pra controle de licenciamento e planejamento de capacidade.

Ex:
```bash
zmprov countAccount dominio.com.br
ou 
zmprov cta dominio.com.br
```

---

#### zmprov createDomain / zmprov cd

**cd** -> create domain.

Ex:
```bash
zmprov createDomain dominio.com.br
ou
zmprov cd dominio.com.br
```

---

#### zmprov deleteDomain / zmprov dd

**dd** -> delete domain.

Ex:
```bash
zmprov deleteDomain dominio.com.br
ou
zmprov dd dominio.com.br
```

---

#### zmprov getDomainInfo / zmprov gdi

Mostra informações de detrminado domínio. Ele precisa que seja digo o tipo de valor Sendo aceito: _name_, _id_, _virtualHostname_ 

Exibe informações gerais do domínio com base no NAME:
```bash
zmprov getDomainInfo name empresa.com.br
ou 
zmprov gdi name empresa.com.br
```



Exibe informações gerais do domínio com base no ID:
```bash
zmprov getDomainInfo id a56da796-0edd-4023-8329-edb344158567
ou
zmprov gdi id a56da796-0edd-4023-8329-edb344158567
```

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
