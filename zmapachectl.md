# zmapachectl


### Sumário

- [Definição](#definição)
- [--help](#--help)
- [status](#status)
- [restart](#restart)
- [start](#start)
- [stop](#stop)


---

#### Definição

O **zmapachectl** controla o serviço Apache HTTP que roda dentro do Zimbra, usado especificamente pra dar suporte a alguns componentes que dependem dele, como o serviço de correção ortográfica (_spell check_) e outras integrações que usam Apache como servidor web auxiliar (diferente do mailboxd, que é Java e atende o webmail/admin console principal).

Útil se o corretor ortográfico parar de responder no webmail (aquele sublinhado vermelho de erro de digitação que costuma aparecer ao escrever e-mails),reiniciar o Apache geralmente resolve.

O Apache HTTP roda na porta **7780** e pode ser conferido com o comando `ss -ltpun | grep http`, e o zmapachectl controla extamente esse serviço e esta porta.

Todos os comandos deste artigo precisam ser executados com o usuário zimbra, comumente usando o comando `su zimbra`.

---

#### --help

Usado para mostar as opções do comando.

```bash
zmapachectl --help
```

---

#### status

Verifica o estado de execução do Apache HTTP.

```bash
zmapachectl status
```

---

#### restart

Reinicia o serviço do Apache HTTP.

Ex:
```bash
zmapachectl restart
```

---

#### start

Inicia o serviço do Apache HTTP.

Ex:
```bash
zmapachectl start
```

---

#### stop

Para o serviço do Apache HTTP.

Ex:
```bash
zmapachectl stop
```

Obs: Se for observar os serviços que estão rodando via `zmcontrol status` será visto que o serviço **spell** está parado, essa informação é vista da seguinte maneira:

```txt
spell      Stopped
           zmapachectl is not running
```

---