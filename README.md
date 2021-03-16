# Git Assignment

**INDIVIDUAL**

**Entrega**: 18-Mar-21

## Como entregar
Copie o arquivo em um repositorio que seja seu e coloque as respostas nas caixas abaixo

Abra uma issue nesse repositório aqui indicando o link para o arquivo no seu repo.

### Entenda o repositorio
Baixe o arquivo [handson.zip] (handson.zip) e descompacte-o
A pasta handson é um repositório git. Usando a linha de comando, altere o diretório para "handson/"

As caixas vazias
```

```
representam o conteúdo que você precisa preencher e postar em seu repositório privado

1. Descreva qual é a saída dos seguintes comandos
    -  `git branch` 
    -  `git checkout BRANCH_NAME` (USE THE NAME OF AN EXISTING BRANCH)
    -  `git log --decorate`

```
1 - git branch  

feature-foo
* master

(lista os branchs)
----------------------------------
2 - git checkout feature-foo 

Switched to branch 'feature-foo'

(muda para o branch escolhido)
----------------------------------
3 - git log --decorate

commit a70a8e9d3c5390e367028faf033f2a9ef03d2e91 (HEAD -> feature-foo)
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:29:22 2018 -0700

    Adding header of method foo()

commit 309b0d73ff9c2163591c9e96e307fe61b4c8f58a
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:27:16 2018 -0700

    Adding class A skeleton

commit 9c1eeb8901b0926ce7fa13cc6ce0a1876fc4179b
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Fri Aug 24 15:26:44 2018 -0700

    Creating all files (all empty)

(log dos commits)
```

2. Tente usar `git log --graph --all`. O que acontece?
```
* commit f67f266cf420735187053f10d32e2c0f7cbc5a43 (master)
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Fri Aug 24 15:30:05 2018 -0700
| 
|     Adding class B skeleton
|   
| * commit a70a8e9d3c5390e367028faf033f2a9ef03d2e91 (HEAD -> feature-foo)
|/  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
|   Date:   Fri Aug 24 15:29:22 2018 -0700
|   
|       Adding header of method foo()
| 
* commit 309b0d73ff9c2163591c9e96e307fe61b4c8f58a
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Fri Aug 24 15:27:16 2018 -0700
| 
|     Adding class A skeleton
| 
* commit 9c1eeb8901b0926ce7fa13cc6ce0a1876fc4179b
  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
  Date:   Fri Aug 24 15:26:44 2018 -0700
  
      Creating all files (all empty)

( representação gráfica em texto dos commits feitos )

```

3. Use `git diff BRANCH_NAME`  para ver as diferenças de um ramo e do ramo atual.
   Sumarize as diferenças do master e do outro ramo.

```
( Diferenças no arquivo 'A.java', no branch 'feature-foo' arquivo 'a' X 'master' arquivo 'b' )

diff --git a/A.java b/A.java
index 3ea227e..674b8ce 100644
--- a/A.java
+++ b/A.java
@@ -1,4 +1,7 @@
 public class A {
-
+   
+   public void foo() {
+   
+   }
 
 }


( Diferenças no arquivo 'B.java', no branch 'feature foo' arquivo 'a' X 'master' arquivo 'b' )

diff --git a/B.java b/B.java
index ae64e6b..e69de29 100644
--- a/B.java
+++ b/B.java
@@ -1,4 +0,0 @@
-public class B {
-
-
-}


```

4. Escreva uma sequencia de comandos para mesclar o ramo não-master no `master`

```
1 - git checkout 'master'
2 - git merge 'feature-foo'

```


5. Escreva um comando (ou sequência) para (i) criar um novo ramo chamado `math` (do` master`)
e (ii) mudar para este ramo

```
1 - git checkout master
2 - git branch math
3 - git checkout math

```
   
6. Edite B.java adicionando o código abaixo ao conteúdo do arquivo
```java
System.out.println("I know math, look:")
System.out.println(2+2)
```

7. Escreva o comando (ou sequencia) para realizar o commit de suas mudanças
```
(como handson é um repositório git, tive que adicionar ele ao repositório que criei)
0 - git remote add SL2021-repo https://github.com/HCelante/SL2021-repo

(processo para realizar o commit)
1 - git add B.java
2 - git commit -m 'modificação no arquivo B.java'
3 - git push

```

8. Volte para o branch `master` e mude B.java adicionando o seguinte código-fonte (confirme sua mudança para` master`):
```java
System.out.println("Hello World")
```

9. Escreva uma sequência de comando para mesclar o branch `math` em` master` e descreva o que aconteceu
```
( comito as modificações no master para o repositório remoto)
1 - git push --set-upstream SL2021-repo master

( agora faço o merge)
2 - git merge math

Mesclagem automática de B.java
CONFLITO (conteúdo): conflito de mesclagem em B.java
Automatic merge failed; fix conflicts and then commit the result.

```
   
10. Escreva um conjunto de comandos para abortar a mesclagem
```
1 - git merge --abort

```
   
11. Agora repita o item 9, mas prossiga com a mesclagem manual (Editando B.java). Todas as funções implementadas são necessárias. Explique o seu procedimento
```
Como uso o Visual Studio Code ele entrega visualmente o conflito do merge:
![merge visualizer](/capmerge.png)

Para fazer manualmente é necessário apagar os marcadores do conflito, manter apenas o que deseja do merge, adicionar o arquivo ao commit e comitar em seguida. No caso do VSCode cliquei em 'accept both' e adicionei o arquivo ao commit e comitei.

1 - git add .
2 - git commit -m 'Conflito resolvido'

```

12. Escreva um comando (ou conjunto de comandos) para prosseguir com a mesclagem e atualizar o branch `master`
```
1 - git push

```



