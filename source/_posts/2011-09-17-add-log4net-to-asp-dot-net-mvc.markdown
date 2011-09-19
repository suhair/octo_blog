---
layout: post
title: "Add Log4net to asp.net Mvc"
date: 2011-09-17 21:36
comments: true
categories: 
---

<div class="container">
	<div class="row">
		<div class="sixcol">&nbsp</div>
		<div class="sixcol last">
            <h1 class="main-head">
                Integrating log4net into asp.net MVC application
            </h1>
        </div>
	</div>
</div>


<div class="container padding40">
	<div class="row">
		<h2>Why logging and why log4net?</h2>
		<div class="eightcol">
            Inserting log statements is a low-tech debugging method. It may be the only way because debuggers will not be available always. 
        </div>
		<div class="fourcol last"></div>
	</div>
</div>


<div class="container padding40">
	<div class="row">
		<h2>Getting Started</h2>
		<div class="eightcol">
            Create a new asp.net MVC application and add reference to log4net.dll directly or through NuGet package manager.

            <pre>
                Install-Package log4net
            </pre>

            <p class="para">Our first goal is to write the application started log. Add the following to the Application_Start method inside the global file and then <kbd>F5</kbd>.</p>

<pre>
    var logger = log4net.LogManager.GetLogger("MVC Application");
    logger.Debug("The application has started");
</pre>

        </div>
		<div class="fourcol last"></div>
	</div>
</div>


<div class="container padding40">
	<div class="row">
		<h2>Building Blocks</h2>
		<div class="eightcol">
            Log4net has three main components, named loggers, appenders, and layouts. Log4net provides the ability to disable certain log statements. Loggers are named entities and thier names are case sensitive. They follow named hierarchy rule much like the .net namespace naming rules. For example "System" is a parent of "System.Text" and an ancestor of "System.Text.StringBuilder". Log4net does not impose any restrictions in naming the loggers, however, the preferred naming is to use the fully qualified name of the class where the logger is defined and hence it provides an overload method of GetLogger that accepts the type of the class as argument instead of a string.

            <p class="para">
                Levels convey the importance of the logging message as determined by the programmer. You create or retrive an existing logger using the <code>GetLogger</code> static method on the <code>LogManager</code>. You can set the level on the log request by using any of the variants of the logging request functions like <code>Fatal</code>, <code>Error</code>, and <code>Info</code>
            </p>
        </div>
		<div class="fourcol last"></div>
	</div>
</div>

<div class="container padding40 gray">
	<div class="row">
		<div class="threecol">
            <h3>Fatal</h3>
            <p class="para">It's rarely used and implies the crash of the application</p>
        </div>
        <div class="twocol">
            <h3>Error</h3>
            <p class="para">
                Error level is used when the application encounters exceptions.
            </p>
        </div>
        <div class="twocol">
            <h3>Warn</h3>
            <p class="para">
                Warn level is used when the application encounters minor errors caused by factors external to the application
            </p>
        </div>
        <div class="twocol">
            <h3>Info</h3>
            <p class="para">
                Info level is used when there is a significant event in the normal life cycle of the application.
            </p>
        </div>
		<div class="threecol last">
            <h3>Debug</h3>
            <p class="para">
                Debug level is used for normal frequently occuring events in the application
            </p>
        </div>
	</div>
</div>


<div class="container padding40">
	<div class="row">	
		<div class="eightcol">
            Log4net provides the ability to print the logging requests to multiple destinations. An output destination is called an Appender. It also allows attaching multiple appenders to any logger. The format of the message could be customized by associating layouts with the appenders. Each appender has its own private layout.
        </div>
		<div class="fourcol last"></div>
	</div>
</div>





