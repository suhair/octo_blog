---
layout: post
title: "Getting Started With Nginx in Ubuntu"
date: 2011-09-19 11:27
comments: true
categories: 
---
<div class="container">
	<div class="row">
		<div class="sixcol"></div>
		<div class="sixcol last">
            <h1 class="main-head">Getting started with NginX on Ubuntu</h1>
        </div>
	</div>
</div>


<div class="container padding40">
	<div class="row">
		<h2>Preparing the stage</h2>
		<div class="eightcol">
            Nginx is written in the C programming language and obviously Gnu Compiler Collection (GCC) must be installed on the server for compiling the Nginx from source. 
<pre>
    apt-get install gcc
</pre>            
<p class="para">
    Another dependency is the Perl Compatible Regular Expression (PCRE) library.
</p>

<pre>
    apt-get install libpcre3 libpcre3-dev
</pre>

<p class="para">
    For gzip compression Nginx depends on the Zlib library
</p>


<pre>
    apt-get install zlib zlib-devel
</pre>


        <p class="para">
            Install openssl for serving the secure pages.
        </p>
<pre>
    apt-get install openssl libssl-dev
</pre>


<p class="para">
    It is time to download the source. Create a directory called nginx_src and download the latest version.
</p>

<pre>
    mkdir nginx_src && cd nginx_src
    wget http://nginx.org/download/nginx-1.0.6.tar.gz
    tar zxf nginx-1.0.6.tar.gz
</pre>


<p class="para">
    Configure Nginx to enable all modules and install the missing libraries as required by running the ./configure .. command and looking for the error messages, untill you can see the configuration summary message.
</p>

<pre>
    cd  nginx-1.0.6
    apt-get install libgd2-xpm-dev
    apt-get install libgeoip-dev
    ./configure --user=www-data --group=www-data
    --with-http_ssl_module
    --with-http_realip_module
    --with-http_addition_module 
    --with-http_xslt_module
    --with-http_image_filter_module 
    --with-http_geoip_module
    --with-http_sub_module
    --with-http_dav_module
    --with-http_flv_module
    --with-http_gzip_static_module 
    --with-http_random_index_module
    --with-http_secure_link_module
    --with-http_stub_status_module


</pre>


    <p class="para">
        Configuration step creates the makefile and it is now time to compile the source. Compiling is as easy as issuing a <code>make</code> command and after successful compilation you should see the following message and you may proceed further for installation as follows:
make[1]: Leaving directory &lt;your nginx path name&gt; The default nginx installation location is <code>/usr/local/nginx/</code>
        
    </p>

<pre>
    make
    make install
</pre>


<div class="para">
    There are two kinds of applications; foreground and background (daeomons) applications and nginx belongs to the later group.
    Let's add a script to manage the nginx.
</div>
<pre>
    wget -O init-deb.sh http://library.linode.com/assets/661-init-deb.sh
    mv init-deb.sh /etc/init.d/nginx
    chmod +x /etc/init.d/nginx
    /usr/sbin/update-rc.d -f nginx defaults    
</pre>


<p class="para">
    In the above step navigate to the /etc/init.d/ folder and edit the nginx file to point the path to proper nginx installation directory. Now the nginx server could be started by issuing the following command.
</p>

<pre>
    /etc/init.d/nginx start
</pre>

<p class="para">
    Now you can verify that nginx is running by visiting the localhost on default port (80).
</p>

        </div>




		<div class="fourcol last"></div>
	</div>
</div>
