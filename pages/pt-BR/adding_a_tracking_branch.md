---
view: page
title: "45. Adicionando um branch de rastreamento"
---

<h3>Metas</h3>

<ul><li>Aprender como adicionar um branch local que rastreia um repositório remoto.</li></ul>

<p>Branches que começam com remotes/origin pertencem ao repositório original.  Perceba que, mesmo que você não tenha mais o branch styles, ele sabe que o branch está no repositório original.</p>

<h2><em>01</em> Adicione um branch local que rastreia um branch remoto.</h2>

<h4 class="h4-pre">Execute:</h4>

<pre class="instructions">git branch --track style origin/style
git branch -a
git hist --max-count=2</pre>

<h4 class="h4-pre">Resultado:</h4>
<pre class="sample">$ git branch --track style origin/style
Branch style set up to track remote branch style from origin.
$ git branch -a
  style
* master
  remotes/origin/HEAD -&gt; origin/master
  remotes/origin/style
  remotes/origin/master
$ git hist --max-count=2
* 2faa4ea 2011-03-09 | Changed README in original repo (HEAD, origin/master, origin/HEAD, master) [Alexander Shvets]
* 6e6c76a 2011-03-09 | Updated index.html (origin/style, style) [Alexander Shvets]</pre>

<p>Agora nós conseguimos ver o branch style na lista de branches e no log.</p>
