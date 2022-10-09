# File and folder permissions

Found here: [https://help.dreamhost.com/hc/en-us/articles/214751018-UNIX-commands-Changing-permissions](https://help.dreamhost.com/hc/en-us/articles/214751018-UNIX-commands-Changing-permissions)

Using the numeric mode, you can assign numbers to each permission. For example:

```
4 = r (read)
2 = w (write)
1 = x (execute)
```

Then, you would add all three together for each owner to get the full value. The following table illustrates the different permissions each owner could possibly have.

| 7 | read, write, and execute ("rwx") | 4 + 2 + 1 = 7 |
| 6 | read and write ("rw-")           | 4 + 2 = 6     |
| 5 | read and execute ("r-x")         | 4 + 0 + 1 = 5 |
| 4 | read only ("r--")                | 4 + 0 + 0 = 4 |
| 3 | write and execute (rare) ("-wx") | 0 + 2 + 1 = 3 |
| 2 | write only (rare) ("-w-")        | 0 + 2 + 0 = 2 |
| 1 | execute only (rare) ("--x")      | 0 + 0 + 1 = 1 |
| 0 | no permissions ("---")           | 0 + 0 + 0 = 0 |

Remember, there are three sets of owners of a file or directory:

- User
- Group
- Public

All three have their own permissions. Thus, all three must now be added together to get the full value.

<table class="wikitable">
<tbody>
<tr>
<th>Command</th>
<th>Permissions</th>
</tr>
<tr>
<td>
<div class="preboxcontainer">
<pre class="prebox"><span class="server">[server]$ </span><span class="command">chmod 600 <span class="code-highlight">file.txt</span></span></pre>
</div>
</td>
<td>
<p><strong>-rw-------</strong></p>
<ul>
<li>Only the User has read and write permissions.</li>
</ul>
</td>
</tr>
<tr>
<td>
<div class="preboxcontainer">
<pre class="prebox"><span class="server">[server]$ </span><span class="command">chmod 700 <span class="code-highlight">dir</span></span></pre>
</div>
</td>
<td>
<p><strong>drwx------</strong></p>
<ul>
<li>Only the Owner has read, write and execute permissions</li>
</ul>
</td>
</tr>
<tr>
<td>
<div class="preboxcontainer">
<pre class="prebox"><span class="server">[server]$ </span><span class="command">chmod 755 <span class="code-highlight">file.txt</span></span></pre>
</div>
</td>
<td>
<p><strong>-rwxr-xr-x</strong></p>
<ul>
<li>The User has read, write and execute permissions.</li>
<li>The Group only has read and execute permissions.</li>
<li>All others have read and execute permissions.</li>
</ul>
</td>
</tr>
<tr>
<td>
<div class="preboxcontainer">
<pre class="prebox"><span class="server">[server]$ </span><span class="command">chmod 644 <span class="code-highlight">file.txt</span></span></pre>
</div>
</td>
<td>
<p><strong>-rw-r--r--</strong></p>
<ul>
<li>The User has read and write permissions.</li>
<li>The Group has read permissions.</li>
<li>Others have read permissions.</li>
</ul>
</td>
</tr>
<tr>
<td>
<div class="preboxcontainer">
<pre class="prebox"><span class="server">[server]$ </span><span class="command">chmod 664 <span class="code-highlight">file.txt</span></span></pre>
</div>
</td>
<td>
<p><strong>-rw-rw-r--</strong></p>
<ul>
<li>The User has read and write permissions.</li>
<li>The Group has read and write permissions.</li>
<li>Others have only read permissions.</li>
</ul>
</td>
</tr>
</tbody>
</table>