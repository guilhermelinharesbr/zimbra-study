# zmlocalconfig


### Sumário

- [Definição](#definição)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [--default / -d](#--default---d)
- [--help / -h](#--help---h)
- [--path / -p](#--path---p)
- [--show / -s](#--show---s)

---

#### Definição

O **zmlocalconfig** é usado para definir ou obter a configuração local de um servidor Zimbra.

---

#### Fonte de Pesquisa

[zmlocalconfig wiki](https://wiki.zimbra.com/wiki/CLI_zmlocalconfig_(Local_Configuration) "Comando zmlocalconfig na Wiki do Zimbra")

---

#### --default / -d

Exibi os valores padrão das configurações locais do Zimbra.

Ex:
```bash
zmlocalconfig --default
ou
zmlocalconfig -d
```

---

#### --help / -h

Exibe a ajuda para as opções de uso desta ferramenta.

Ex:
```bash
zmlocalconfig --help
ou
zmlocalconfig -h
```

---

#### --path / -p

Mostra qual arquivo de configuração será usado. Geramente um arquivo XML.

Ex:
```bash
zmlocalconfig --path
ou
zmlocalconfig -p
```

Saída:

```txt
/opt/zimbra/conf/localconfig.xml
```

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


