# zmcbpolicydctl


### Sumário

- [Definição](#definição)
- [Fonte de Pesquisa](#fonte-de-pesquisa)
- [--help](#--help)
- [status](#status)
- [restart](#restart)

---

#### Definição

O **zmcbpolicydctl** controla o serviço cbpolicyd (Cluebringer Policy Daemon), um servidor de políticas para o Postfix, usado principalmente pra fazer rate limiting (controle de taxa de envio) e outras regras de política de e-mail, como limitar quantas mensagens um usuário pode enviar por hora/dia, prevenindo uma conta ser usada para spam em massa.

---

#### Fonte de Pesquisa

[zmcbpolicydctl wiki](https://wiki.zimbra.com/wiki/CBPolicyD_Management "Comando zmcbpolicydctl na Wiki do Zimbra")

---

#### --help

Usado para mostar as opções do comando.

```bash
zmcbpolicydctl --help
```

---

#### status

Verifica o estado do daemon do Policyd.

Ex:
```bash
su zimbra
zmcbpolicydctl status
```

---

#### restart

Reinicia o serviço do PolicyD/cbpolicyd.

Ex:
```bash
zmcbpolicydctl restart
```

---
