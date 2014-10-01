```html
<html>
<head>
<title>visio2python - Draw your Program in Microsoft Visio</title>
<meta name="keywords" content="visio2pyhon, microsoft visio, python, converter, automat, state machine, program, ">
<meta name="description" content="visio2python - Draw your Program">
</head>
<body>
<div id="content">
<table width=60% align=center><tr><td align=justify>

<h1>visio2python - Draw your Program in Microsoft Visio</h1>

<p>
I would like here to tell you about another way to write programs.
Certainly nothing fundamentally new in science, I will not open.
But I created a utility called <b>visio2python</b> that really helps me during development of 
<a href="http://datahaven.net">DataHaven.NET</a> project, so it might be usefull for other developers.
</p>

<p>
The tool <b>visio2python</b> generates <a href="http://python.org">Python</a> code from graphical diagrams created in 
<a href="http://en.wikipedia.org/wiki/Microsoft_Visio">Microsoft Visio</a>. 
So you can "draw" your idea, press the button, execute the code and see how it works. 
Less code, more visualisation, fast development, more stability.
</p>

<p>
The key here is the use of <a href="http://en.wikipedia.org/wiki/Finite-state_machine">finite state machines</a> 
to describe the algorithm of the program. 
This approach also known as <a href="http://en.wikipedia.org/wiki/Automata-Based_Programming">Automata-Based Programming</a>.
My professor <a href="http://en.wikipedia.org/wiki/Anatoly_Shalyto">Anatoly Abramovich Shalyto</a> 
gave me this knowledge - 
in those wonderful days when I was 
<a href="http://en.ifmo.ru/">at university</a>. Great Thanks to Him!.
</p>

<p>
Anatoly Abramovich Shalyto is a Russian scientist, doctor of sciences, professor, 
awarded by Russian State Government in 2008 for achievements in education, 
developer of technology for Automata-based programming named "Switch-technology", 
initiator of <a href="http://www.codeproject.com/gen/design/nifopd.asp">Open Project Documentation Initiative</a>
and of <a href="http://www.savethebest.ru/">"Save the best in the universities of Russia"</a>. 
</p>

<p>
Let's see how it looks on the picture. On the picture below you see a transition graph of state machine for  
<a href="http://en.wikipedia.org/wiki/Automata-Based_Programming#Example">this sample program</a> 
taken from the article above,
I draw it using <a href="http://datahaven.net/visio2python/automats.vss">this Microsoft Visio stancil</a>.
</p>

<img src="raw/master/automat1.png">

Here is:
<ul>
    <li>three states: <b>BEFORE</b>, <b>INSIDE</b> and <b>AFTER</b>,</li>
    <li>one event: <font color=red>input-char</font>,</li>
    <li>three condition methods: <font color=green>isNewLine()</font>, <font color=green>isSpace()</font> and <font color=green>isAnyChar()</font>,</li>
    <li>one action method: <font color=blue>doPutChar()</font>.</li>
</ul>

<p>
Using <b>visio2python</b> I generate Python code for this drawing.
</p>

<img src="raw/master/visio2python-screen1.png">

<p>
It was written in the file ./generated/Automat_1.py, here is the file contents:
</p>

<pre><font face="Lucida,Courier New"><font color="#C00000">from</font> <font color="#000000">automat</font> <font color="#C00000">import</font> <font color="#000000">Automat</font>

<font color="#000000">_Automat1</font> <font color="#0000C0">=</font> <font color="#000000">None</font>
<font color="#C00000">def</font> <font id="A" color="#000000">A</font><font color="#0000C0">(</font><font color="#000000">event</font><font color="#0000C0">=</font><font color="#000000">None</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">=</font><font color="#000000">None</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
    <font color="#C00000">global</font> <font color="#000000">_Automat1</font>
    <font color="#C00000">if</font> <font color="#000000">_Automat1</font> <font color="#C00000">is</font> <font color="#000000">None</font><font color="#0000C0">:</font>
        <font color="#008000"># set automat name and starting state here
</font>        <font color="#000000">_Automat1</font> <font color="#0000C0">=</font> <font color="#000000">Automat1</font><font color="#0000C0">(</font><font color="#004080">'Automat_1'</font><font color="#0000C0">,</font> <font color="#004080">'BEFORE'</font><font color="#0000C0">)</font>
    <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#C00000">is</font> <font color="#C00000">not</font> <font color="#000000">None</font><font color="#0000C0">:</font>
        <font color="#000000">_Automat1</font><font color="#0000C0">.</font><font color="#000000">automat</font><font color="#0000C0">(</font><font color="#000000">event</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font>
    <font color="#C00000">return</font> <font color="#000000">_Automat1</font>

<font color="#C00000">class</font> <font color="#000000">Automat1</font><font color="#0000C0">(</font><font color="#000000">Automat</font><font color="#0000C0">)</font><font color="#0000C0">:</font>

    <font color="#008000"># EVENTS:
</font>    <font color="#008000"># input-char
</font>
    <font color="#C00000">def</font> <font id="A" color="#000000">A</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">event</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font id="BEFORE" color="#008000">#---BEFORE---
</font>        <font color="#C00000">if</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'BEFORE'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isNewLine</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isAnyChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'INSIDE'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isSpace</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#C00000">pass</font>
        <font id="INSIDE" color="#008000">#---INSIDE---
</font>        <font color="#C00000">elif</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'INSIDE'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isSpace</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'AFTER'</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isAnyChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isNewLine</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'BEFORE'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
        <font id="AFTER" color="#008000">#---AFTER---
</font>        <font color="#C00000">elif</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'AFTER'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isNewLine</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'BEFORE'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#0000C0">(</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isAnyChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#C00000">or</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isSpace</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#C00000">pass</font>

    <font color="#C00000">def</font> <font id="isAnyChar" color="#000000">isAnyChar</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">pass</font>

    <font color="#C00000">def</font> <font id="isSpace" color="#000000">isSpace</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">pass</font>

    <font color="#C00000">def</font> <font id="isNewLine" color="#000000">isNewLine</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">pass</font>

    <font color="#C00000">def</font> <font id="doPutChar" color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">pass</font><font color="#000000"></font></font></pre>

<p>
This is an automatically generated code, a template to create a complete program.
</p>

<p>
Class <b><code>Automat1</code></b> is a sub class of base class 
<a href="http://datahaven.net/visio2python/automat.py"><b><code>automat.Automat</code></b></a> which runs the state machine.
</p>

<p>
Method <b><code>A(event, arg)</code></b> and global variable <b><code>_Automat1</code></b> is a 
<a href="http://en.wikipedia.org/wiki/Singleton_pattern">singletone pattern</a> 
to have only one instance of the state machine. 
Let's say to call this state machine from outside you use:
</p>

<pre>
Automat_1.A('some-event', some_arguments)
</pre>

<p>
If you need to start many copies of same automat - remove this method and variable definition and use it like any other class:
</p>

<pre>
a1 = Automat_1.Automat1('automat1', 'BEFORE') # call constructor
a1.automat('some-event', some_arguments)      # fire event in the automat
a2 = Automat_1.Automat1('automat2', 'BEFORE')
a2.automat('some-event', some_arguments)                            
</pre>

<p>
Let's write a code for conditions, actions and reading/writing loop. 
Here's the complete working code, which is identical to the example in the article.
</p>

<pre><font color="#C00000">from</font> <font color="#000000">automat</font> <font color="#C00000">import</font> <font color="#000000">Automat</font>

<font color="#C00000">class</font> <font color="#000000">Automat1</font><font color="#0000C0">(</font><font color="#000000">Automat</font><font color="#0000C0">)</font><font color="#0000C0">:</font>

    <font color="#008000"># EVENTS:
</font>    <font color="#008000"># input-char
</font>
    <font color="#C00000">def</font> <font id="A" color="#000000">A</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">event</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font id="BEFORE" color="#008000">#---BEFORE---
</font>        <font color="#C00000">if</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'BEFORE'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isNewLine</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isAnyChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'INSIDE'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isSpace</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#C00000">pass</font>
        <font id="INSIDE" color="#008000">#---INSIDE---
</font>        <font color="#C00000">elif</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'INSIDE'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isSpace</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'AFTER'</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isAnyChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isNewLine</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'BEFORE'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
        <font id="AFTER" color="#008000">#---AFTER---
</font>        <font color="#C00000">elif</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'AFTER'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isNewLine</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'BEFORE'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'input-char'</font> <font color="#C00000">and</font> <font color="#0000C0">(</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isAnyChar</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#C00000">or</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">isSpace</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font> <font color="#0000C0">)</font> <font color="#0000C0">:</font>
                <font color="#C00000">pass</font>

    <font color="#C00000">def</font> <font id="isAnyChar" color="#000000">isAnyChar</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">return</font> <font color="#000000">arg</font> <font color="#0000C0">!=</font> <font color="#004080">'\n'</font> <font color="#C00000">and</font> <font color="#000000">arg</font> <font color="#0000C0">!=</font> <font color="#004080">' '</font>

    <font color="#C00000">def</font> <font id="isSpace" color="#000000">isSpace</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">return</font> <font color="#000000">arg</font> <font color="#0000C0">==</font> <font color="#004080">' '</font>

    <font color="#C00000">def</font> <font id="isNewLine" color="#000000">isNewLine</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">return</font> <font color="#000000">arg</font> <font color="#0000C0">==</font> <font color="#004080">'\n'</font>

    <font color="#C00000">def</font> <font id="doPutChar" color="#000000">doPutChar</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#000000">sys</font><font color="#0000C0">.</font><font color="#000000">stdout</font><font color="#0000C0">.</font><font color="#000000">write</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>

<font color="#C00000">def</font> <font id="main" color="#000000">main</font><font color="#0000C0">(</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
    <font face="Lucida,Courier New"><font color="#C00000">import</font> <font color="#000000">sys</font>
    <font color="#000000">a1</font> <font color="#0000C0">=</font> <font color="#000000">Automat1</font><font color="#0000C0">(</font><font color="#004080">'a1'</font><font color="#0000C0">,</font> <font color="#004080">'BEFORE'</font><font color="#0000C0">,</font> <font color="#0080C0">1</font><font color="#0000C0">,</font> <font color="#000000">open</font><font color="#0000C0">(</font><font color="#004080">'log.txt'</font><font color="#0000C0">,</font> <font color="#004080">'w'</font><font color="#0000C0">,</font> <font color="#0080C0">1</font><font color="#0000C0">)</font><font color="#0000C0">)</font>
    <font color="#C00000">while</font> <font color="#000000">True</font><font color="#0000C0">:</font>
        <font color="#000000">c</font> <font color="#0000C0">=</font> <font color="#000000">sys</font><font color="#0000C0">.</font><font color="#000000">stdin</font><font color="#0000C0">.</font><font color="#000000">read</font><font color="#0000C0">(</font><font color="#0080C0">1</font><font color="#0000C0">)</font>
        <font color="#C00000">if</font> <font color="#000000">c</font> <font color="#0000C0">==</font> <font color="#004080">''</font><font color="#0000C0">:</font>
            <font color="#C00000">break</font>
        <font color="#000000">a1</font><font color="#0000C0">.</font><font color="#000000">automat</font><font color="#0000C0">(</font><font color="#004080">'input-char'</font><font color="#0000C0">,</font> <font color="#000000">c</font><font color="#0000C0">)</font>

<font color="#C00000">if</font> <font color="#000000">__name__</font> <font color="#0000C0">==</font> <font color="#004080">'__main__'</font><font color="#0000C0">:</font>
    <font color="#000000">main</font><font color="#0000C0">(</font><font color="#0000C0">)</font><font color="#000000"></font></font></pre>
<p>
You see how simple is to write conditions and actions methods. No chance to make a mistake.
</p>

<p>
Take the file <b>automat.py</b> from the 
<a href="http://datahaven.net/visio2python.tar.gz"><b>visio2python</b> distribution</a>, 
place it in the same folder and run the code to test it.
</p>

<pre>
C:\work\visio2python>python Automat_1.py
abcd efgh 1234
abcd
  Test Test Test
Test
LONG_line_with_no_spaces
LONG_line_with_no_spaces
 1 2 3 4 5
1
^C
</pre>

<p>
You see the program works fine, it prints the first word from the input line and skip leading spaces.<br>
I know, this is very simple example but I just want to show you how to use <b>visio2python</b> here.
More complex examples you can found on the 
<a href="http://datahaven.net/automats.html">DataHaven.NET web site</a>.
</p>

<p>
Let me describe the expressions syntax and diagram rules.
<ul>
    <li>states are placed in the round boxes and written with <b>CAPITAL</b> laters,</li>
    <li>events are <font color=red>red</font>,</li>
    <li>condition are <font color=green>green</font>, starts with '<b>is</b>' and ends with <b>'()'</b> to looks like a Python methods,</li>
    <li>actions are <font color=blue>blue</font>, starts with '<b>do</b>' and ends with <b>'()'</b>,</li>
    <li>actions are separated from conditions with single <u>underline</u>,</li>
    <li><b>and</b>, <b>or</b> and <b>not</b> operators may be used to construct complex conditions,</li>
    <li>you can also use expressions like <b>Z in [ <font color=green>x</font> , <font color=green>y</font> ]</b> or 
        <b>Z not in [ <font color=green>x</font> , <font color=green>y</font> ]</b>.</li>
    <li>you can combine conditional expressions with parentheses - <b>'('</b> and <b>')'</b> ,</li>
    <li>to separate actions use a semicolon - <b>';'</b>,</li>
    <li>variables can be used in conditions and actions like <font color=green>indexA>=4</font> or <font color=blue>counterB+=1</font>,</li>
    <li>you can check another state machine's state with expression like this <font color=#808000>automat2().state</font> is <font color=green>STATE_01</font>,</li>
    <li>event <i>"state changed"</i> from another automat can be catched using expression like this <font color=red>automat2.state</font> is <font color=green>STATE_02</font>,</li>
    <li>you can fire event in another state machine like this <font color=#808000>automat2(</font><font color=red>event01</font><font color=#808000>)</font>,</li>
    <li>use stancil called <i>LABEL</i> to set automat name ( use only <b>lower letters</b> and <b>'_'</b>, finished with <b>'()'</b> ), 
       or set page name in the dialog <b>File->Page Setup->Page properties</b> in Microsoft Visio.</li>
</ul>
I tried to make the expressions syntax as close as possible to Python language. 
</p>

<p>
Even more useful usage of the class <b><code>automat.Automat</code></b> you can found in 
<a href="http://twistedmatrix.com/">Twisted</a> applications. 
</p>
<p>
Typically, you have a lot of calls to <b><code>reactor.callLater(seconds, callable)</code></b> method, 
and it breaks the application logic into many pieces all around the code.
<br> 
Calling <b><code>reactor.callLater(delay1, B)</code></b> from <b><code>A()</code></b>
and <b><code>reactor.callLater(delay2, A)</code></b> from <b><code>B()</code></b> is
fairly typical situation. 
</p>

<p>
What exactly happens at a certain time and 
how to understand the current situation become quite difficult sometimes. 
To all this is added the use of a set of variables which control the program behavior
and debugging in such situations takes a lot of time and nerves.
</p>

<p>
In the class <b><code>automat.Automat</code></b> you can use a timer event and pass it into conditions. 
Let's see another sample that simulates a traffic light. Here is a state machine:
</p>

<img src="raw/master/automat2.png">

<p>
And working code:
</p>

<pre><font face="Lucida,Courier New"><font color="#C00000">from</font> <font color="#000000">automat</font> <font color="#C00000">import</font> <font color="#000000">Automat</font>

<font color="#000000">_TrafficLightController</font> <font color="#0000C0">=</font> <font color="#000000">None</font>
<font color="#C00000">def</font> <font id="A" color="#000000">A</font><font color="#0000C0">(</font><font color="#000000">event</font><font color="#0000C0">=</font><font color="#000000">None</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">=</font><font color="#000000">None</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
    <font color="#C00000">global</font> <font color="#000000">_TrafficLightController</font>
    <font color="#C00000">if</font> <font color="#000000">_TrafficLightController</font> <font color="#C00000">is</font> <font color="#000000">None</font><font color="#0000C0">:</font>
        <font color="#008000"># set automat name and starting state here
</font>        <font color="#000000">_TrafficLightController</font> <font color="#0000C0">=</font> <font color="#000000">TrafficLightController</font><font color="#0000C0">(</font><font color="#004080">'traffic_light_controller'</font><font color="#0000C0">,</font> <font color="#004080">'TURNED_OFF'</font><font color="#0000C0">)</font>
    <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#C00000">is</font> <font color="#C00000">not</font> <font color="#000000">None</font><font color="#0000C0">:</font>
        <font color="#000000">_TrafficLightController</font><font color="#0000C0">.</font><font color="#000000">automat</font><font color="#0000C0">(</font><font color="#000000">event</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font>
    <font color="#C00000">return</font> <font color="#000000">_TrafficLightController</font>

<font color="#008000"># traffic_light_controller() Automat
</font><font color="#C00000">class</font> <font color="#000000">TrafficLightController</font><font color="#0000C0">(</font><font color="#000000">Automat</font><font color="#0000C0">)</font><font color="#0000C0">:</font>

    <font color="#008000"># EVENTS:
</font>    <font color="#008000"># switch-off
</font>    <font color="#008000"># switch-on
</font>    <font color="#008000"># timer-10sec
</font>    <font color="#008000"># timer-15sec
</font>    <font color="#008000"># timer-3sec
</font>
    <font color="#000000">timers</font> <font color="#0000C0">=</font> <font color="#0000C0">{</font>
        <font color="#004080">'timer-3sec'</font><font color="#0000C0">:</font> <font color="#0000C0">(</font><font color="#0080C0">3</font><font color="#0000C0">,</font> <font color="#0000C0">[</font><font color="#004080">'YELLOW'</font><font color="#0000C0">]</font><font color="#0000C0">)</font><font color="#0000C0">,</font>
        <font color="#004080">'timer-10sec'</font><font color="#0000C0">:</font> <font color="#0000C0">(</font><font color="#0080C0">10</font><font color="#0000C0">,</font> <font color="#0000C0">[</font><font color="#004080">'RED'</font><font color="#0000C0">]</font><font color="#0000C0">)</font><font color="#0000C0">,</font>
        <font color="#004080">'timer-15sec'</font><font color="#0000C0">:</font> <font color="#0000C0">(</font><font color="#0080C0">15</font><font color="#0000C0">,</font> <font color="#0000C0">[</font><font color="#004080">'GREEN'</font><font color="#0000C0">]</font><font color="#0000C0">)</font><font color="#0000C0">,</font>
        <font color="#0000C0">}</font>

    <font color="#C00000">def</font> <font id="A" color="#000000">A</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">event</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font id="TURNED_OFF" color="#008000">#---TURNED_OFF---
</font>        <font color="#C00000">if</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'TURNED_OFF'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'switch-on'</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'RED'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doRedLight</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
        <font id="RED" color="#008000">#---RED---
</font>        <font color="#C00000">elif</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'RED'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'switch-off'</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'TURNED_OFF'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doStop</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'timer-10sec'</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'YELLOW'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doYellowLight</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
        <font id="YELLOW" color="#008000">#---YELLOW---
</font>        <font color="#C00000">elif</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'YELLOW'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'switch-off'</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'TURNED_OFF'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doStop</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'timer-3sec'</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'GREEN'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doGreenLight</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
        <font id="GREEN" color="#008000">#---GREEN---
</font>        <font color="#C00000">elif</font> <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#C00000">is</font> <font color="#004080">'GREEN'</font><font color="#0000C0">:</font>
            <font color="#C00000">if</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'timer-15sec'</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'RED'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doRedLight</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>
            <font color="#C00000">elif</font> <font color="#000000">event</font> <font color="#0000C0">==</font> <font color="#004080">'switch-off'</font> <font color="#0000C0">:</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">state</font> <font color="#0000C0">=</font> <font color="#004080">'TURNED_OFF'</font>
                <font color="#000000">self</font><font color="#0000C0">.</font><font color="#000000">doStop</font><font color="#0000C0">(</font><font color="#000000">arg</font><font color="#0000C0">)</font>

    <font color="#C00000">def</font> <font id="doRedLight" color="#000000">doRedLight</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">print</font> <font color="#000000">time</font><font color="#0000C0">.</font><font color="#000000">asctime</font><font color="#0000C0">(</font><font color="#0000C0">)</font><font color="#0000C0">,</font> <font color="#004080">'red'</font>

    <font color="#C00000">def</font> <font id="doGreenLight" color="#000000">doGreenLight</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">print</font> <font color="#000000">time</font><font color="#0000C0">.</font><font color="#000000">asctime</font><font color="#0000C0">(</font><font color="#0000C0">)</font><font color="#0000C0">,</font> <font color="#004080">'green'</font>

    <font color="#C00000">def</font> <font id="doYellowLight" color="#000000">doYellowLight</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#C00000">print</font> <font color="#000000">time</font><font color="#0000C0">.</font><font color="#000000">asctime</font><font color="#0000C0">(</font><font color="#0000C0">)</font><font color="#0000C0">,</font> <font color="#004080">'yellow'</font>

    <font color="#C00000">def</font> <font id="doStop" color="#000000">doStop</font><font color="#0000C0">(</font><font color="#000000">self</font><font color="#0000C0">,</font> <font color="#000000">arg</font><font color="#0000C0">)</font><font color="#0000C0">:</font>
        <font color="#000000">reactor</font><font color="#0000C0">.</font><font color="#000000">stop</font><font color="#0000C0">(</font><font color="#0000C0">)</font>


<font color="#C00000">import</font> <font color="#000000">time</font>
<font color="#C00000">from</font> <font color="#000000">twisted</font><font color="#0000C0">.</font><font color="#000000">internet</font> <font color="#C00000">import</font> <font color="#000000">reactor</font>
<font color="#000000">reactor</font><font color="#0000C0">.</font><font color="#000000">callWhenRunning</font><font color="#0000C0">(</font><font color="#000000">A</font><font color="#0000C0">,</font> <font color="#004080">'switch-on'</font><font color="#0000C0">)</font>
<font color="#000000">reactor</font><font color="#0000C0">.</font><font color="#000000">callLater</font><font color="#0000C0">(</font><font color="#0080C0">60</font><font color="#0000C0">,</font> <font color="#000000">A</font><font color="#0000C0">,</font> <font color="#004080">'switch-off'</font><font color="#0000C0">)</font>
<font color="#000000">reactor</font><font color="#0000C0">.</font><font color="#000000">run</font><font color="#0000C0">(</font><font color="#0000C0">)</font><font color="#000000"></font></font></pre>

<p>
The class <b><code>automat.Automat</code></b> is designed in a such way that every timer is started <b>only when it is needed</b>.
This is to decrease the amount of dellayed calls and to not consume extra resources.
For example, <font color=red>timer-10sec</font> in the example above 
is started when state machine riched state <b>RED</b>.
</p>

<p>
The timers is generated automatically, syntax is <b>timer-{number}{sec|min|hour}</b>.
For seconds you can use values less than 1 and omit point.
For example: 
<font color=red>timer-25sec</font>, 
<font color=red>timer-5min</font>, 
<font color=red>timer-3hour</font>, 
<font color=red>timer-004sec</font>, 
<font color=red>timer-0.2sec</font>.
</p>

<p>
The <b><code>automat.Automat</code></b> is a <a href="http://en.wikipedia.org/wiki/Thread_safety">thread-safe</a> class, 
so you can use it in a multi-threaded applications without any locks.
There is no blocking code in the class body, but <b>writing conditions and actions is your deal</b>.
You can use different methods to write threaded applications controlled with state machines, 
for example use <b><code>reactor.callInThread()</code></b>.
</p>

<p>
It must be noted that <b>visio2python</b> use colors to split expressions on the transition graph arcs 
and so right color values should be used to get correct result.
In Microsoft Visio open dialog <b>Tools->Color Palette</b> and check color indexes. 
Here is a table of used colors, 
your palette should have same indexes and values to be compatible with <b>visio2python</b>.
</p>
<table align=center border=1 cellspacing=0 cellpadding=5>
<tr><th>index</th><th>name</th><th>value</th><th>used for</th></tr>
<tr><td>0</td><td>black</td><td>0,0,0</td><td>all other characters</td></tr>
<tr><td>2</td><td>red</td><td>128,0,0</td><td>events</td></tr>
<tr><td>9</td><td>green</td><td>0,128,0</td><td>conditions</td></tr>
<tr><td>10</td><td>blue</td><td>0,0,128</td><td>actions</td></tr>
<tr><td>11</td><td>gold</td><td>128,128,0</td><td>automats</td></tr>
</table>
<p>
Well, actually this is standard system colors, so just do not change anything and it should work.
Just need to be sure you are using right colors for conditions, actions, events and automats. 
Mine palette looks like this:
</p>

<div align=center><img src="raw/master/color-palette.png"></div>

<p>
After you did generated the Python code for your future program you will need to modify it to make it working, 
write conditions, actions and other things.
After some time you may want to modify the logic of your program and so change something 
in the Microsoft Visio document.
No problem - there is a <b>Step 3</b> in the <b>visio2python</b> tool to update the existing code. <br>
Set a destination to your working program generated from this MS Visio document and press the button <b>Merge with existing Python code</b>.
It should read and scan all Python files in that location and update code for subclasses of automat.Automat class.
</p>

<p>
I am using Microsoft Visio 2007 to draw transition graphs, 
I hope <b>visio2python</b> is compatible with other versions.<br>
You can even run Microsoft Visio on Ubuntu <a href="http://appdb.winehq.org/appview.php?appId=119">using WineHQ</a>, I did it for my self.
</p>

<p>
This tool is written in Microsoft Visual Basic 6.0.
Download <b>visio2python</b> distribution <a href="http://datahaven.net/visio2python.tar.gz">here</a>.
</p>

</td></tr></table>
</div>
</body>
</html>
```