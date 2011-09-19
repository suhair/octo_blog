---
layout: post
title: "Essential Extjs4"
date: 2011-09-11 16:35
comments: true
categories: 
---
<div class="container">
	<div class="row">
		<div class="sixcol">&nbsp;</div>
        <div class="sixcol last">
        	<h1 class="main-head">Essential ExtJs 4 to survive</h1>
        </div>
	</div>

    


</div>



<div class="container padding40">
            <div class="row">
                <h2>
                    Querying the Dom elements
                
                </h2>
                <div class="eightcol">
                <p class="para">DomQuery interface of ExtJS 4 supports most of the CSS3 selector spec. <code>selectNode</code> selects a single element based on the given CSS or XPATH expression, while <code>select</code> gathers a group of elements matching the expression. selectNode returns a single <code>Element</code>. </p>
                
                <p class="para">
                    <code>Element</code> encapsulates DOM element; adds simple DOM manipulation facilities, and normalizes browser differences. It also inherits from <code>Ext.fx.Anim</code> making visual effects easily available for the DOM elements. <code>addListener</code> or its equivalent <code>on</code> shorthand method appends an event handler to the element. <code>Ext.get</code> retrieves the element by its id or by node.
                </p>


                <pre>
var el = Ext.get('elementId');
el.on('click', this.onElementClick, this, {
    single: false,           
    stopEvent : true            
});
</pre>
    






    	    </div>
    </div>




    <div class="container padding40">
    	
        <div class="row">
            <h2>Controller</h2>
        	<div class="eightcol">
            
            <p class="para">
                Controllers binds the application as a cohesive unit. They listen for events from the view and take action based on it. Every controller extends the functionality of <code>Ext.app.Controller</code>. On application booting <code>init</code> method of the controller will be called by the framework provided the controller is placed in the controllers array of the application.
            </p>

            
            </div>
        	<div class="fourcol"></div>
        </div>
    </div>


    <div class="container padding40">
    	<div class="row">
    		<h2>Ext.ClassManager</h2>
    		<div class="eightcol"
                Ext.ClassManager as the name suggests, manages all the classes and handles the mapping from string class name to actual objects throughout the framework. It is accessed through the following shortcuts.
                <ol>
                	<li>Ext.define</li>
                	<li>Ext.create</li>
                	<li>Ext.widget</li>
                	<li>Ext.getClass</li>
                	<li>Ext.getClassName</li>
                </ol>

                <p class="para">
                    <code>Ext.define</code> defines a class and accepts three parameters; the string dot namespaced class name, the object of properties to apply for this class, and an optional callback to execute after the class is created. For naming a class the root and the class name are CamelCased and everything else is lowercased. 
                </p>
            </div>
    		<div class="fourcol last"></div>
    	</div>
    </div>


<div class="container padding40">
	<div class="row">
		<h2>Ext.form.Panel</h2>
		<div class="eightcol">
            FormPanel provides standard container for forms. FormPanel is configured with the Anchor layout by default. It accepts all the configuration options associated with the BasicForm class through the <code>initialConfig</code> property.
        </div>
		<div class="fourcol last"></div>
	</div>
</div>



