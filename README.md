# Padrão Commits Sebrae [![starline](https://starlines.qoo.monster/assets/gists/5dfcdf8eec66a051ecd85625518cfd13)](https://sebraepr.com.br)

Veja como [a menor alteração](#tipos) na mensagem do seu commit pode fazer a diferença
<br />
<img src="https://firebasestorage.googleapis.com/v0/b/natureatoz-5286d.appspot.com/o/images%2Freview.png?alt=media" alt="Profile Image" width="100%" style="max-width: 100%; height: 300px;">


> [!WARNING]
> **Todos os commits devem ser feitos em Inglês**
 
### Padrões
<pre>
<b><a href="#types">&lt;type&gt;</a></b></font>(<b><a href="#scopes">&lt;optional scope&gt;</a></b>): <b><a href="#description">&lt;description&gt;</a></b>
<sub>empty separator line</sub>
<b><a href="#body">&lt;optional body&gt;</a></b>
<sub>empty separator line</sub>
<b><a href="#footer">&lt;optional footer&gt;</a></b>
</pre>
 
### Merge Commit
<pre>
Merge branch '<b>&lt;branch name&gt;</b>'
</pre>
<sup>Seguindo padrões git merge message</sup>

### Revert Commit
<pre>
Revert "<b>&lt;reverted commit subject line&gt;</b>"
</pre>
<sup>Seguindo padrões git revert message</sup>

### Inital Commit 
```
chore: init
```

### Tipos
* Alterações relevantes na API
    * `feat` Commits, que adiciona ou remove um novo recurso
    * `fix` Commits, que corrige um bug
* `refactor` Commits, que reescreve/reestrutura seu código, mas não altera nenhum comportamento da API
* `perf` São commits `refactor` especiais, que melhoram performance/desempenho
* `style` Commits, que não afetam o significado (espaço em branco, formatação, ponto e vírgula ausentes, etc.)
* `test` Commits, que adicionam testes ausentes ou corrigem testes existentes
* `docs` Commits, que afetam apenas a documentação
* `build` Commits, que afetam componentes de build como ferramenta de build, pipeline de CI, dependências, versão do projeto, ...
* `ops` Commits, que afetam componentes operacionais como infraestrutura, implantação, backup, recuperação, ...
* `chore` modificando arquivos de versionamento, exemplo: `.gitignore`

### Escopo
O `escopo` fornece informações contextuais adicionais.
 
* É uma parte **opcional** do formato
* Os escopos permitidos dependem do projeto específico
* Não use identificadores de problemas como escopos

### Indicador de Mudanças de Quebra

Mudanças drásticas devem ser indicadas por um `!` antes do `:` na linha de assunto, por exemplo `feat(api)!: remove status endpoint`
* É uma parte opcional do formato


### Descrição
A `description` contém uma descrição concisa da mudança.
* É uma parte **obrigatória** do formato
* Use o imperativo, presente: "change" não "changed" nem "changes"
* Pense em `This commit will...` ou `This commit should...`
* Não coloque a primeira letra em maiúscula
* Sem ponto (`.`) no final


### Body
 O `body` deve incluir a motivação para a mudança e contrastar isso com o comportamento anterior.
* É uma parte **opcional** do formato
* Este é o lugar para mencionar identificadores de problemas e suas relações


### Footer
O `Footer` deve conter qualquer informação sobre **Breaking Changes** e também é o lugar para **referenciar Issues** aos quais este commit se refere.
* É uma parte **opcional** do formato
* **opcionalmente** referencia um issue pelo seu id.
* **Breaking Changes** deve começar com a palavra `BREAKING CHANGES:` seguida por um espaço ou duas quebras de linha. O restante da mensagem de commit é então usado para isso.


### Exemplos
* ```
  feat: add email notifications on new direct messages
  ```
* ```
  feat(shopping cart): add the amazing button
  ```
* ```
  feat!: remove ticket list endpoint

  refers to JIRA-1337

  BREAKING CHANGES: ticket enpoints no longer supports list all entites.
  ```
* ```
  fix(shopping-cart): prevent order an empty shopping cart
  ```
* ```
  fix(api): fix wrong calculation of request body checksum
  ```
* ```
  fix: add missing parameter to service call

  The error occurred because of <reasons>.
  ```
* ```
  perf: decrease memory footprint for determine uniqe visitors by using HyperLogLog
  ```
* ```
  build: update dependencies
  ```
* ```
  build(release): bump version to 1.0.0
  ```
* ```
  refactor: implement fibonacci number calculation as recursion
  ```
* ```
  style: remove empty line
  ```

---

<br />

 
<img src="https://transparencia.sebrae.com.br/static/media/slogo-azul.97b61ad7.png" alt="Profile Image" width="280" height="150">
