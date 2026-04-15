<div align="center">

# 🕵️ HunterRedirect

<sub>Lightweight open redirect scanner for bug bounty and security testing.</sub>

<br>

<img src="image.png" width="260" style="border-radius:10px; box-shadow: 0 0 20px #ff0000;" />

<br><br>

<img src="https://img.shields.io/badge/version-0.0.1-ff0000?style=for-the-badge&logo=github&logoColor=black" />
<img src="https://img.shields.io/badge/python-3.x-ff0000?style=for-the-badge&logo=python&logoColor=black" />
<img src="https://img.shields.io/badge/status-active-ff0000?style=for-the-badge&logo=hackthebox&logoColor=black" />

</div>

---

<div style="background-color:#0d1117; padding:18px; border-radius:12px; border:1px solid #ff0000; font-family:monospace;">

<h3 style="color:#ff0000;">⚡ Features</h3>

<ul>
<li>Automated Open Redirect detection</li>
<li>Mass fuzzing with payloads</li>
<li>Multi-threaded scanning</li>
<li>Stdin support (pipeline friendly)</li>
<li>Custom wordlist support</li>
<li>Verbose debugging mode</li>
</ul>

---

<h3 style="color:#ff0000;">🛠️ Requirements</h3>

<ul>
<li>Python 3.x</li>
<li>requests</li>
</ul>

---

<h3 style="color:#ff0000;">🛠️ Installation</h3>

<pre style="color:#ff0000;">
git clone https://github.com/yHunterDep/HunterRedirect.git
cd HunterRedirect
chmod +x hunter_redirect
</pre>

---

<h3 style="color:#ff0000;">🚀 Usage</h3>

<pre style="color:#ff0000;">
./hunter_redirect -u "http://target.com/?url=FUZZ"

# with wordlist
./hunter_redirect -u "http://target.com/?redirect=FUZZ" -w payloads.txt

# increase threads
./hunter_redirect -u "http://target.com/?next=FUZZ" -c 50

# verbose
./hunter_redirect -u "http://target.com/?url=FUZZ" -v
</pre>

---

<h3 style="color:#ff0000;">🔑 FUZZ</h3>

<p>The keyword <b>FUZZ</b> must be placed inside parameter values.<br>
HunterRedirect replaces it with payloads during testing.</p>

<pre style="color:#ff0000;">
http://target.com/?url=FUZZ
http://target.com/?next=FUZZ
</pre>

---

<h3 style="color:#ff0000;">🔗 Pipeline (Bug Bounty)</h3>

<pre style="color:#ff0000;">
gau target.com | grep "=" | qsreplace 'FUZZ' | ./hunter_redirect
cat urls.txt | grep "=" | qsreplace 'FUZZ' | gf lfi | ./hunter_redirect | anew results_redirect.txt
</pre>

---

<h3 style="color:#ff0000;">🎯 Output</h3>

<pre style="color:#ff0000;">
[FOUND REDIRECT] http://target.com/?url=//evil.com ===> https://evil.com
</pre>

---

<h3 style="color:#ff4d4d;">⚠️ Disclaimer</h3>

<p>For authorized testing only.</p>

</div>
