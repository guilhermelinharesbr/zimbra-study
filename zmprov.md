# zmprov


### Sumário

- [Definição](#definição)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [Opções Gerais](#opções-gerais)
- [zmprov --help / zmprov -h](#zmprov---help--zmprov--h)
- [Comandos de provisionamento de DOMÍNIO](#comandos-de-provisionamento-de-domínio)
- [countAccount / cta](#countaccount--cta)
- [createDomain / cd](#createdomain--cd)
- [deleteDomain / dd](#deletedomain--dd)
- [getDomain / gd](#getdomain--gd)
- [getDomainInfo / gdi](#getdomaininfo--gdi)
- [getAllDomains / gad](#getalldomains--gad)
- [modifyDomain / md](#modifydomain--md)
- [Comandos de provisionamento de CONTAS](#comandos-de-provisionamento-de-contas)
- [addAccountAlias / aaa](#addaccountalias--aaa)
- [checkPasswordStrength / cps](#checkpasswordstrength--cps)
- [createAccount / ca](#createaccount--ca)
- [deleteAccount / da](#deleteaccount--da)
- [getAccount / ga](#getaccount--ga)
- [getAllAccounts / gaa](#getallaccounts--gaa)
- [getAllAdminAccounts / zmprov gaaa](#getalladminaccounts--zmprov-gaaa)
- [zmprov modifyAccount / zmprov ma](#zmprov-modifyaccount--zmprov-ma)
- [zmprov removeAccountAlias / zmprov raa](#zmprov-removeaccountalias--zmprov-raa)
- [zmprov setPassword / zmprov sp](#zmprov-setpassword--zmprov-sp)
- [Comandos de provisionamento de LISTAS DE DISTRIBUIÇÃO](#comandos-de-provisionamento-de-listas-de-distribuição)
- [zmprov createDistributionList / zmprov cdl](#zmprov-createdistributionlist--zmprov-cdl)
- [zmprov addDistributionListMember / zmprov adlm](#zmprov-adddistributionlistmember--zmprov-adlm)
- [zmprov removeDistributionListMember / zmprov rdlm](#zmprov-removedistributionlistmember--zmprov-rdlm)
- [zmprov getAlldistributionLists / zmprov gadl](#zmprov-getalldistributionlists--zmprov-gadl)
- [zmprov getDistributionListmembership / zmprov gdlm](#zmprov-getdistributionlistmembership--zmprov-gdlm)
- [zmprov getDistributionList / zmprov gdl](#zmprov-getdistributionlist--zmprov-gdl)
- [zmprov modifyDistributionList / zmprov mdl](#zmprov-modifydistributionlist--zmprov-mdl)
- [zmprov deleteDistributionList / zmprov ddl](#zmprov-deletedistributionlist--zmprov-ddl)
- [zmprov addDistributionListAlias / zmprov adla](#zmprov-adddistributionlistalias--zmprov-adla)
- [zmprov removeDistributionListAlias / zmprov rdla](#zmprov-removedistributionlistalias--zmprov-rdla)
- [zmprov renameDistributionList / zmprov rdl](#zmprov-renamedistributionlist--zmprov-rdl)
- [Comandos de provisionamento de COMPARTILHAMENTO](#)
- [getShareInfo / gsi](#getshareinfo--gsi)
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

#### countAccount / cta

Serve pra contar quantas contas existem em um domínio, agrupadas por Classe de Serviço (COS), útil principalmente pra controle de licenciamento e planejamento de capacidade.

Ex:
```bash
zmprov countAccount dominio.com.br
ou 
zmprov cta dominio.com.br
```

---

#### createDomain / cd

**cd** -> create domain.

Ex:
```bash
zmprov createDomain dominio.com.br
ou
zmprov cd dominio.com.br
```

---

#### deleteDomain / dd

**dd** -> deleteDomain.

Ex:
```bash
zmprov deleteDomain dominio.com.br
ou
zmprov dd dominio.com.br
```

---

#### getDomain / gd

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

#### getDomainInfo / gdi

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

#### getAllDomains / gad

**gad** -> getAllDomains.

Ex:
```bash
zmprov getAllDomains
ou
zmprov gad
```

---

#### modifyDomain / md

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

#### addAccountAlias / aaa 

Cria um apelido(alias) para a conta.

{name@domain|id|adminName} {alias@domain}

Ex. ao mandar um email para guilherme\@dominio.com.br a conta guilherme.linhares\@dominio.com.br:

```bash
zmprov addAccountAlias guilherme.linhares@dominio.com.br guilherme@dominio.com.br
ou
zmprov aaa guilherme.linhares@dominio.com.br guilherme@dominio.com.br
```

---

#### checkPasswordStrength / cps

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

#### createAccount / ca

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

#### deleteAccount / da 

Deleta uma conta de email:
```bash
zmprov da guilherme.linhares@dominio.com.br
```

---

#### getAccount / ga

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

#### getAllAccounts / gaa

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

#### zmprov setPassword / zmprov sp

Altera a senha.

Ex:
```bash
zmprov setPassword guilherme.linhares@dominio.com.br @senha123
ou
zmprov sp guilherme.linhares@dominio.com.br senha%123
```

---

#### Comandos de provisionamento de LISTAS DE DISTRIBUIÇÃO

Comandos que são usados para criação, configuração, etc das listas de distribuição no Zimbra. 

---

#### zmprov createDistributionList / zmprov cdl

Cria uma lista de distribuição.

Ex. de criar a lista de distribuição já com o display name:
```bash
zmprov cdl equipe.financeiro@dominio.com.br displayName "Equipe do Financeiro"
zmgsautil forceSync -a galsync@dominio.com.br -n zimbra
```

Obs.: O segundo comando é usado para forçar sincronizar a nova lista na GAL.

---

#### zmprov addDistributionListMember / zmprov adlm

Adiciona um membro em uma lista de distribuição.

Syntax: {list@domain|id} {member@domain}

Ex:
```bash
zmprov addDistributionListMember equipe.financeiro@dominio.com.br guilherme.linhares@dominio.com.br
ou
zmprov adlm equipe.financeiro@dominio.com.br guilherme.linhares@dominio.com.br
```

---

#### zmprov removeDistributionListMember / zmprov rdlm

Remove um membro em uma lista de distribuição.

Syntax: {list@domain|id} {member@domain}

Ex:
```bash
zmprov removeDistributionListMember equipe.financeiro@dominio.com.br guilherme.linhares@dominio.com.br
ou
zmprov rdlm equipe.financeiro@dominio.com.br guilherme.linhares@dominio.com.br
```

---

#### zmprov getAlldistributionLists / zmprov gadl

Exibi todas as listas de distribuição.

Ex. todas as listas de distribuição independete do domínio:

```bash
zmprov getAlldistributionLists
ou
zmprov gadl
```

Ex2. todas as listas de distribuição apenas do domínio dominio\.com.br:

```bash
zmprov getAlldistributionLists dominio.com.br
ou
zmprov gadl dominio.com.br
```

Ex3. mostrando mais detalhes das listas de distribuição:

```bash
zmprov getAlldistributionLists -v
zmprov gadl dominio.com.br -v
```

Obs: Ao upsar a opção `-v` são exibidos mais detalhes como quantidade de membros, email dos membros, etc.

---

#### zmprov getDistributionListmembership / zmprov gdlm

Exibi os membros das listas de distribuição.

Ex:

```bash
zmprov getDistributionListmembership equipe.financeiro@dominio.com.br
ou
zmprov gdlm equipe.financeiro@dominio.com.br
```

---

#### zmprov getDistributionList / zmprov gdl

Mostra informações de uma lista de distribuição, como ID, membros, quando foi criada, se está habilitada ou desabilitada, etc.

Ex:

```bash
zmprov gdl equipe.financeiro@dominio.com.br 
```

Ex2. serve para exportar a lista de todos os membros (e-mails) do grupo equipe.financeiro\@dominio.com.br para dentro de um arquivo de texto chamado saida-zmprov.txt:

```bash
zmprov gdl lista@dnocs.gov.br > saida-zmprov.txt
```

---

#### zmprov modifyDistributionList / zmprov mdl

Usado para editar atirbutos de uma lista de distribuição.

Syntax: {list@domain|id} attr1 value1 {attr2 value2...}

Ex. mudando a descrição de uma lista:

```bash
zmprov modifyDistributionList equipe.financeiro@dominio.com.br  description "Lista usada para mandar emails para os colaboradores do setor Financeiro"
```

Ex2. mudando o display name de uma lista:

```bash
zmprov mdl equipe.financeiro@dominio.com.br displayName "Equipe Financeiro"
```

---

#### zmprov deleteDistributionList / zmprov ddl

Deleta uma lista de distribuição.

Syntax: {list@domain|id}

Ex:

```bash
zmprov deleteDistributionList equipe.financeiro@dominio.com.br
ou
zmprov ddl equipe.financeiro@dominio.com.br
```

---

#### zmprov addDistributionListAlias / zmprov adla

Adiciona um apelido(alias) para uma lista de distribuição.

Syntax: {list@domain|id} {alias@domain}

Ex. cria o alias colaboradores.financeiro\@dominio.com.br para a lista equipe.financeiro\@dominio.com.br:

```bash
zmprov addDistributionListAlias equipe.financeiro@dominio.com.br colaboradores.financeiro@dominio.com.br
ou
zmprov adla equipe.financeiro@dominio.com.br colaboradores.financeiro@dominio.com.br
```

---

#### zmprov removeDistributionListAlias / zmprov rdla

Remove um apelido(alias) para uma lista de distribuição.

Syntax: {list@domain|id} {alias@domain}

Ex. remove o alias colaboradores.financeiro\@dominio.com.br para a lista equipe.financeiro\@dominio.com.br:

```bash
zmprov removeDistributionListAlias equipe.financeiro@dominio.com.br colaboradores.financeiro@dominio.com.br
ou
zmprov rdla equipe.financeiro@dominio.com.br colaboradores.financeiro@dominio.com.br
```

---

#### zmprov renameDistributionList / zmprov rdl

Renomeia uma lista de distribuição.

Syntax: {list@domain|id} {newName@domain}

Ex. renomeando a lista de distribuição equipe.financeiro\@dominio.com.br para apenas financeiro\@dominio.com.br:

```bash
zmprov renameDistributionList equipe.financeiro@dominio.com.br financeiro@dominio.com.br
ou
zmprov rdl equipe.financeiro@dominio.com.br financeiro@dominio.com.br
```

---

### Comandos de provisionamento de COMPARTILHAMENTO



---

#### getShareInfo / gsi 

Esse comando retorna informações sobre compartilhamentos publicados, quando o proprietário é especificado, o servidor percorre a mailbox dele pra descobrir todos os compartilhamentos aplicáveis. A saída inclui todos os campos importantes: id do dono, e-mail do dono, id da pasta, caminho completo da pasta, tipo de visualização, direitos concedidos, tipo de concessão (grantee), id e nome do concessionário.

Ex:
```bash
zmprov getShareInfo financeiro@dominio.com.br
ou
zmprov gsi financeiro@dominio.com.br
```

---
