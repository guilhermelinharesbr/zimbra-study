# zmzimletctl


### Sumário

- [Definição](#definição)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [listZimlets](#listzimlets)
- [listPriority](#listpriority)

---

#### Definição

O **zmzimletctl** é a ferramenta de linha de comando no Zimbra utilizada para gerenciar Zimlets no servidor.
Os **zimlets** são add-ons ou extensões do Zimbra que adicionam novas funcionalidades e integrações na interface web (como integrações com videoconferência, anexos do Nextcloud, temas, integrações de chat, etc.).

---

#### Fonte de Pesquisa

[zmzimletctl wiki](https://wiki.zimbra.com/wiki/CLI_zmzimletctl "Comando zmzimletctl na Wiki do Zimbra")

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
