# zmzimletctl


### Sumário

- [Definição](#definição)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [enable](#enable)
- [disable](#disable)
- [acl](#acl)
- [listAcls](#listacls)
- [listZimlets](#listzimlets)
- [listPriority](#listpriority)

---

#### Definição

O **zmzimletctl** é a ferramenta de linha de comando no Zimbra utilizada para gerenciar Zimlets no servidor.
Os **Zimlets** são add-ons ou extensões do Zimbra que adicionam novas funcionalidades e integrações na interface web (como integrações com videoconferência, anexos do Nextcloud, temas, integrações de chat, etc.).

---

#### Fonte de Pesquisa

[zmzimletctl wiki](https://wiki.zimbra.com/wiki/CLI_zmzimletctl "Comando zmzimletctl na Wiki do Zimbra")


--- 

#### enable

Habilita um zimlet.

Syntax: zmzimletctl enable {zimlet}

Ex:
```bash
su zimbra
zmzimletctl enable com_zimbra_ymemoticons
```

---

#### disable

Desabilita um zimlet.

Syntax: zmzimletctl disable {zimlet}

Ex:
```bash
su zimbra
zmzimletctl disable com_zimbra_ymemoticons
```

---

#### acl

Muda a ACL para o Zimlet em uma COS, podendo forncer permissão ou remover.

Syntax: {zmzimletctl acl} {zimlet} {cos1} grant|deny 

Ex. colocando a permissão do zimlet com_zimbra_ymemoticons na COS de nome default:
```bash
su zimbra
zmzimletctl acl com_zimbra_ymemoticons default grant
```

Ex2. negando a permissão do zimlet com_zimbra_ymemoticons na COS de nome default:
```bash
su zimbra
zmzimletctl acl com_zimbra_ymemoticons default deny
```

---

#### listAcls

Lista as ACLS para os Zimlets, ou melhor lista as COS que possuem o Zimlet ativado.

Syntax: {zmzimletctl listAcls} {zimlet}

Ex. Vendo as permissões do zimlet com_zimbra_ymemoticons:
```bash
su zimbra
zmzimletctl listAcls com_zimbra_ymemoticons
```

Saída: 
`Listing COS entries for Zimlet com_zimbra_ymemoticons...
	default
	default_persona`

---

#### listZimlets

Mostra todos os zimlets instalados, com o status de cada um (enabled, disabled, etc.), além de dizer os zimlets disponíveis por COS.

Ex:
```bash
su zimbra
zmzimletctl listZimlets
```

---

#### listPriority

Mostra as prioridades do zimlets (0 é alto, 9 é baixo).

Ex:
```bash
su zimbra
zmzimletctl listPriority
```

---
