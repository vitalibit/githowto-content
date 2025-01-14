---
view: page
title: "16. Desfazendo commits"
---

<h3>Metas</h3>

<ul><li>Aprender como desfazer commits no repositório local.</li></ul>

<h2><em>01</em> Desfazendo commits</h2>

<p>Algumas vezes você percebe que os novos commits estão errados e você quer desfazê-los. Existem várias maneiras de resolver esse problema, mas nós usamos a mais segura aqui.</p>

<p>Para desfazer o commit, vamos criar um novo commit desfazendo as modificações não desejadas.</p>

<h2><em>02</em> Edite o arquivo e faça um commit</h2>

<p>Substitua o arquivo <code>hello.html</code> com o seguinte.</p>

<h4 class="h4-pre">Arquivo: <em>hello.html</em></h4>

<pre class="file">&lt;html&gt;
  &lt;head&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;Hello, World!&lt;/h1&gt;
    <strong>&lt;!-- This is an unwanted but committed change --&gt;</strong>
  &lt;/body&gt;
&lt;/html&gt;</pre>

<h4 class="h4-pre">Execute:</h4>

<pre class="instructions">git add hello.html
git commit -m "Oops, we didn't want this commit"</pre>

<h2><em>03</em> Faça um commit com as novas modificações que desfazem as modificações anteriores</h2>

<p>Para desfazer o commit, precisamos criar um commit que deleta as modificações feitas pelo commit indesejado.</p>

<h4 class="h4-pre">Execute:</h4>

<pre class="instructions">git revert HEAD</pre>

<p>Vá para o editor, onde você consegue editar a mensagem padrão do commit ou deixá-la como está. Salve e feche o arquivo.</p>

<p>Você verá &#8230;</p>

<h4 class="h4-pre">Resultado:</h4>

<pre class="sample">$ git revert HEAD --no-edit
[master 45fa96b] Revert "Oops, we didn't want this commit"
 1 files changed, 1 insertions(+), 1 deletions(-)</pre>

<p>Já que desfizemos o último commit, nós podemos usar <code>HEAD</code> como o argumento para desfazê-lo. Nós podemos cancelar qualquer commit no histórico, apontando seu hash.</p>

<p class="note"><strong>Nota:</strong> O comando <code>--no-edit</code> pode ser ignorado. Ele era desnecessário para gerar as informações de saída sem abrir o editor.</p>

<h2><em>04</em> Confira o log</h2>

<p>Conferir o log mostra os cancelamentos e commits indesejados no nosso repositório.</p>

<h4 class="h4-pre">Execute:</h4>

<pre class="instructions">git hist</pre>

<h4 class="h4-pre">Resultado:</h4>

<pre class="sample">$ git hist
* 45fa96b 2011-03-09 | Revert "Oops, we didn't want this commit" (HEAD, master) [Alexander Shvets]
* 846b90c 2011-03-09 | Oops, we didn't want this commit [Alexander Shvets]
* fa3c141 2011-03-09 | Added HTML header (v1) [Alexander Shvets]
* 8c32287 2011-03-09 | Added standard HTML page tags (v1-beta) [Alexander Shvets]
* 43628f7 2011-03-09 | Added h1 tag [Alexander Shvets]
* 911e8c9 2011-03-09 | First Commit [Alexander Shvets]</pre>

<p>Essa técnica pode ser aplicada para qualquer commit (mas podem surgir conflitos). É seguro usá-la mesmo em branches públicos de repositórios remotos.</p>

<h2><em>05</em> Próximo</h2>

<p>A seguir vamos olhar a técnica que pode ser usada para remover o último commit do histórico do repositório.</p>
