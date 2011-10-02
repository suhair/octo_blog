---
layout: post
title: "Learning to Authenticate With Devise"
date: 2011-10-01 19:37
comments: true
categories: 
---
<div class="container">
  <div class="row">
    <div class="sixcol">&nbsp;</div>
    <div class="sixcol last">
      <h1 class="main-head">Learning to Authenticate with Devise</h1>
    </div>
  </div>
</div>


<div class="container padding40">
	<div class="row">
		<div class="eightcol">
                  The first step is to create a new rails application and bundle the devise gem inside it. Devise comes with a generator and it will configure the application and will walk you through the necessary steps. Run <code>rails g devise:install</code>. As instructed by the generator, you should add the configuration for mailer in the development environment, should add a root url, and should have the markup to display the flash messages. It's time to generate the model for representing the application users by running <code>rails g devise User</code>. The previous command will create the following.
<ol>
	<li>User model</li>
	<li>Unit test file</li>
	<li>User fixture</li>
	<li>User migration file</li>
	<li>Route for users</li>
</ol>

<p class="para">
  After including the devise modules in the model and the migration file migrate the database updates and run the rails application.`
</p>


                </div>
		<div class="fourcol last"></div>
	</div>
</div>
