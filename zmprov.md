# zmprov


### Sumário

- [Definição](#definição)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [Opções Gerais](#opções-gerais)
- [zmprov --help / zmprov -h](#zmprov---help--zmprov--h)
- [Comandos de provisionamento de DOMÍNIO](#comandos-de-provisionamento-de-domínio)
- [zmprov countAccount / zmprov cta](#zmprov-countaccount--zmprov-cta)
- [zmprov createDomain / zmprov cd](#zmprov-createdomain--zmprov-cd)
- [zmprov deleteDomain / zmprov dd](#zmprov-deletedomain--zmprov-dd)
- [zmprov getDomain / zmprov gd](#zmprov-getdomain--zmprov-gd)
- [zmprov getDomainInfo / zmprov gdi](#zmprov-getdomaininfo--zmprov-gdi)
- [zmprov getAllDomains / zmprov gad](#zmprov-getalldomains--zmprov-gad)
- [zmprov modifyDomain / zmprov md](#zmprov-modifydomain--zmprov-md)
- [Comandos de provisionamento de CONTAS](#comandos-de-provisionamento-de-contas)
- [zmprov addAccountAlias / zmprov aaa](#zmprov-addaccountalias--zmprov-aaa)
- [zmprov checkPasswordStrength / zmprov cps](#zmprov-checkpasswordstrength--zmprov-cps)
- [zmprov createAccount / zmprov ca](#zmprov-createaccount--zmprov-ca)
- [zmprov deleteAccount / zmprov da](#zmprov-deleteaccount--zmprov-da)
- [zmprov getAccount / zmprov ga](#zmprov-getaccount--zmprov-ga)
- [zmprov getAllAccounts / zmprov gaa](#zmprov-getallaccounts--zmprov-gaa)
- [getAllAdminAccounts / zmprov gaaa](#getalladminaccounts--zmprov-gaaa)
- [zmprov modifyAccount / zmprov ma](#zmprov-modifyaccount--zmprov-ma)
-[zmprov removeAccountAlias / zmprov raa](#zmprov-removeaccountalias--zmprov-raa)
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

### Comandos de provisionamento de DOMÍNIO

Comandos que são usados para criação, configuração, etc dos domínios no Zimbra. 

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

**dd** -> deleteDomain.

Ex:
```bash
zmprov deleteDomain dominio.com.br
ou
zmprov dd dominio.com.br
```

---

#### zmprov getDomain / zmprov gd

**gd** -> getDomain.

Mostra inúmeras informações sobre um domínio.

Ex:
```bash
zmprov getDomain empresa.com.br
ou
zmprov gd empresa.com.br
```

Para descobrir o ID do domínio:
```bash
zmprov getDomain empresa.com.br zimbraId
ou
zmprov gd empresa.com.br zimbraId
```

Para descobrir o domínio de um ID:
```bash
zmprov getDomain 5679d38a-2bc5-4f76-a4e0-ea218d879567 zimbraId
ou
zmprov gd 5679d38a-2bc5-4f76-a4e0-ea218d879567 zimbraId
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

#### zmprov getAllDomains / zmprov gad

**gad** -> getAllDomains.

Ex:
```bash
zmprov getAllDomains
ou
zmprov gad
```

---

#### zmprov modifyDomain / zmprov md

**md** -> modifyDomain

Serve pra alterar atributos de configuração de um domínio já existente.

Ex. Modifica a descrição do domínio:
```bash
zmprov modifyDomain empresa.com.br description "Empresa XYZ"
ou
zmprov md empresa.com.br description "Empresa XYZ"
```

---

### Comandos de provisionamento de CONTAS

Comandos que são usados para criação, configuração, etc das contas no Zimbra. 

---

#### zmprov addAccountAlias / zmprov aaa 

Cria um apelido(alias) para a conta.

{name@domain|id|adminName} {alias@domain}

Ex. ao mandar um email para guilherme\@dominio.com.br a conta guilherme.linhares\@dominio.com.br:

```bash
zmprov addAccountAlias guilherme.linhares@dominio.com.br guilherme@dominio.com.br
ou
zmprov aaa guilherme.linhares@dominio.com.br guilherme@dominio.com.br
```

---

#### zmprov checkPasswordStrength / zmprov cps 

Checa a força/complexidade da senha.

Syntax: {name@domain|id} {password}

Ex:
```bash
zmprov checkPasswordStrength guilherme.linhares@dominio.com.br Pa$$word123
```
Saída: Password passed strength check.

Ex2:
```bash
zmprov cps guilherme.linhares@dominio.com.br 123
```
Saída: ERROR: account.INVALID_PASSWORD (invalid password: too short)

Obs: Este comando não checa a idade ou histórico de senha.

---

#### zmprov createAccount / zmprov ca

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

#### zmprov deleteAccount / zmprov da 

Deleta uma conta de email:
```bash
zmprov da guilherme.linhares@dominio.com.br
```

---

#### zmprov getAccount / zmprov ga

Serve para puxar todos os dados de uma conta específica. Ele aceita tanto o e-mail (guilherme.linhares\@dominio.com.br) quanto o UUID.

Syntax:{name@domain|id|adminName}

Ex. para descobrir qual é o endereço de e-mail associado ao UUID:
```bash
zmprov getAccount 567b0e1a-dddc-461a-b567-617aa189a567 | head -n 1
```

Ex2. para descobrir qual é o endereço de e-mail associado ao UUID:
```bash
zmprov ga 567b0e1a-dddc-461a-b567-617aa189a567 name
```

Ex3. conferindo Frist Name, Last Name e Display Name da conta:
```bash
zmprov ga guilherme.linhares@dominio.com.br givenName sn displayName
```

Ex4. mostra o ID da conta:
```bash
zmprov ga guilherme.linhares@dominio.com.br zimbraId
```

---

#### zmprov getAllAccounts / zmprov gaa

**gaa** -> getAllAccounts.

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

#### getAllAdminAccounts / zmprov gaaa 

Mostra todas as contas Admin:
```bash
zmprov getAllAdminAccounts
ou
zmprov gaaa
```

---

#### zmprov modifyAccount / zmprov ma

Bloqueia uma conta:
```bash
zmprov ma guilherme.linhares@dominio.com.br zimbraAccountStatus locked
```

Desbloqueia uma conta:
```bash
zmprov ma guilherme.linhares@dominio.com.br zimbraAccountStatus active
```

---

#### zmprov removeAccountAlias / zmprov raa

Remove um apelido(alias) de uma conta.

{name@domain|id|adminName} {alias@domain}

Ex. Removendo o apelido guilherme\@dominio.com.br da conta guilherme.linhares\@dominio.com.br:
```bash
zmprov removeAccountAlias guilherme.linhares@dominio.com.br guilherme@dominio.com.br
ou
zmprov raa guilherme.linhares@dominio.com.br guilherme@dominio.com.br
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
