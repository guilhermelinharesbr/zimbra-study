# zmlocalconfig


### Sumário

- [Definição](#definição)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [--show / -s](#--show---s)

---

#### Definição

O **zmlocalconfig** é usado para definir ou obter a configuração local de um servidor Zimbra.

---

#### Fonte de Pesquisa

[zmlocalconfig wiki](https://wiki.zimbra.com/wiki/CLI_zmlocalconfig_(Local_Configuration) "Comando zmlocalconfig na Wiki do Zimbra")

---

#### --show / -s

Força a exibição das strings de senha.

Ex. mostra a senha do usuário **root** com acesso ao MySQL/MariaDB do Zimbra:
```bash
zmlocalconfig --show mysql_root_password
ou
zmlocalconfig -s mysql_root_password
```

Ex2. mostra a senha do usuário **zimbra** com acesso ao MySQL/MariaDB do Zimbra:
```bash
zmlocalconfig --show zimbra_mysql_password
ou
zmlocalconfig -s zimbra_mysql_password
```

---


