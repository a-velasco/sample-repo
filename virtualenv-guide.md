---


---

<h1 id="creating-a-python-virtual-environment">Creating A Python Virtual Environment</h1>
<p><code>virtualenv</code> is a tool for creating isolated Python environments. (<a href="https://virtualenv.pypa.io/en/stable/">Virtualenv documentation</a>)</p>
<p>We use this tool to help manage several dependencies and library versions for different projects. With <code>virtualenv</code>, these changes are easily available to other developers without causing conflicts with other Python projects.</p>
<p>This guide contains the steps to install, set up, and test our team’s virtual environment on <strong>Windows</strong>.</p>
<h2 id="requirements">Requirements</h2>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> <a href="https://www.python.org/downloads/windows/"><strong>Python 3.7 or greater</strong></a>.<br>
You can check your version on a <em>Windows command line</em> with the command <code>python --version</code></li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> <a href="https://phoenixnap.com/kb/install-pip-windows#ftoc-heading-2"><strong>pip</strong></a> package manager</li>
</ul>
<h2 id="installing-virtualenv">Installing <code>virtualenv</code></h2>
<ol>
<li>
<p><strong>On a <em>Windows command line</em>, install the</strong> <code>virtualenv</code> <strong>module</strong></p>
<p><code>pip install virtualenv</code></p>
</li>
<li>
<p><strong>Locate your local Python distribution.</strong></p>
<p>The default path is usually <strong><code>C:\%LocalAppData%\Programs\Python\Python39\python.exe</code></strong></p>
<blockquote>
<p>⚠️ If you have trouble finding your distribution, check the <a href="#my-python-distribution-is-not-located-at-the-default-path">FAQ</a>.</p>
</blockquote>
</li>
<li>
<p><strong>Navigate to your project directory with</strong> <code>cd</code> <strong>and create a new virtual environment with the path to your Python distribution</strong><br>
<code>virtualenv —python [path to python.exe] venv</code></p>
</li>
<li>
<p><strong>Activate the newly created virtual environment</strong><br>
<code>.\venv\Scripts\activate</code></p>
</li>
<li>
<p><strong>Download the latest <code>requirements.txt</code> from</strong> <a href="http://github.com/a-velasco/sample-repo">github.com/a-velasco/sample-repo</a> <strong>to your project directory</strong>. This file contains the python modules and versions that are used in this virtual environment. It should be regularly checked for updates.</p>
<blockquote>
<p>⚠️ If you cannot access this repository, check the <a href="#i-dont-have-access-to-the-repository">FAQ</a>.</p>
</blockquote>
</li>
<li>
<p><strong>Install packages</strong><br>
<code>pip install -r requirements.txt</code></p>
</li>
</ol>
<p>The virtual environment is ready to use! <strong>To exit, use the</strong> <code>deactivate</code> <strong>command on the same shell.</strong></p>
<h2 id="faq">FAQ</h2>
<h4 id="my-python-distribution-is-not-located-at-the-default-path.-how-do-i-find-it">My Python distribution is not located at the default path. How do I find it?</h4>
<p>You can search for your distribution with Python’s <code>sys</code> module.<br>
Open a <em>Python shell</em> and run the commands shown below. The output paths will show the installation directory of your Python distribution.</p>
<pre><code>&gt;&gt;&gt; import sys
&gt;&gt;&gt; for p in sys.path: print(p)
...

C:\Users\MyUsername\AppData\Local\Programs\Python\Python39\python39.zip
C:\Users\MyUsername\AppData\Local\Programs\Python\Python39\DLLs
C:\Users\MyUsername\AppData\Local\Programs\Python\Python39\lib
C:\Users\MyUsername\AppData\Local\Programs\Python\Python39
C:\Users\MyUsername\AppData\Local\Programs\Python\Python39\lib\site-packages
</code></pre>
<h4 id="i-have-a-python-distribution.-why-doesnt-my-command-line-recognize-it">I have a Python distribution. Why doesn’t my command line recognize it?</h4>
<p>First, make sure you are running your <em>Windows CLI</em> as administrator.<br>
If this issue persists, it is likely your Python distribution needs to be added to your <code>PATH</code> environment variable.<br>
Check out the official <a href="https://docs.python.org/3/using/windows.html">Using Python on Windows</a> documentation.</p>
<h4 id="how-do-i-know-if-my-modules-were-installed-correctly-in-the-venv">How do I know if my modules were installed correctly in the venv?</h4>
<p>To see all installed modules, use the command <code>pip freeze</code> while <code>virtualenv</code> is active. The output will contain the modules present in <strong><code>requirements.txt</code></strong>, as shown below.</p>
<pre><code>(venv) C:\Users\MyUsername\Documents\MyProject&gt;pip freeze
asgiref==3.7.2
blinker==1.6.2
click==8.1.4
colorama==0.4.6
contourpy==1.1.0
cycler==0.11.0
Flask==2.3.2
...

(venv) C:\Users\MyUsername\Documents\MyProject&gt;type requirements.txt
asgiref==3.7.2
blinker==1.6.2
click==8.1.4
colorama==0.4.6
contourpy==1.1.0
cycler==0.11.0
Flask==2.3.2
...
</code></pre>
<h4 id="how-do-i-get-access-to-the-repository">How do I get access to the repository?</h4>
<p>If you have a Github account but do not have permission to access the repository, please contact the IT department at<br>
<a href="mailto:it@company.com">it@company.com</a>.</p>

