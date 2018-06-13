---


---

<h1 id="simple-interface-for-instructorsstudents">Simple Interface for Instructors/Students</h1>
<p><strong>MTurk and Qualtrics Integration</strong><br>
<strong>June 13, 2018</strong></p>
<h2 id="goal">Goal</h2>
<p>Primarily, we want a <em>simple, intuitive</em> interface for instructors and students to:</p>
<ol>
<li>Set up a psychological study in <strong>Qualtrics</strong></li>
<li>Collect data through <strong>MTurk</strong></li>
<li><strong>Visualize data</strong> (from <a href="http://Qualtrics.com">Qualtrics.com</a>) as it comes in
<ul>
<li>Do various simple plots</li>
</ul>
</li>
<li><strong>Download data</strong> for any other demonstrations</li>
</ol>
<p>More completely, here’s the general process that we’ll want the program to go through for each request:</p>
<pre><code>mermaid("
sequenceDiagram
  FrontEnd-&gt;&gt;BackEnd: Set survey parameters
  BackEnd-&gt;&gt;Qualtrics: Create survey
  Qualtrics-&gt;&gt;BackEnd: Return survey address
  BackEnd-&gt;&gt;MTurk: Create online data collection ticket
  MTurk--&gt;&gt;BackEnd: Communicate collection status, finished status
  Qualtrics--&gt;&gt;FrontEnd: Stream incoming data. Display results.
  MTurk-&gt;&gt;BackEnd: Confirm finished
  Qualtrics-&gt;&gt;FrontEnd: Display final data, simple plots.
  Qualtrics-&gt;&gt;FrontEnd: Download all data")
</code></pre>
<p><img src="./FlowChart.png" alt="FlowChart"></p>

