---
layout: post
title: "Up and Running With Gvim"
date: 2011-09-08 07:14
comments: true
categories: 
---


<div class="container">
    <div class="row">
        <div class="sixcol">&nbsp;</div>
        <div class="sixcol last">
            <h1 class="main-head">
            Up & Running with gVim like a Boss</h1>
        </div>
    </div>

    <div class="row">
        <div>
            <blockquote cite="http://www.vim.org"> 
                <p> Vim isn't an editor designed to hold its users' hands. It is a tool, the use of which must be learned.</p> &mdash;
                <small>http://www.vim.org</small>
            </blockquote>
        </div>
    </div>


    <div class="row">
        <h2>Installation & Basics</h2>
        <div class="eightcol">
            <p class="para">Grab your copy of gVim from the official vim website and v7.3 is the lastest one. This article assumes that you are using windows operating system and are comfortable with marginal use of Git.</P>

            <p class="para">After the installation you may start console version of Vim by issuing the command <code>vim</code> and the GUI version by issuing the command <code>gvim</code>.</p> 

            












        </div>

        <div class="fourcol last right-align">
            <a href="http://www.vim.org/download.php">Download Vim</a>
            <p><code>vim</code></p>
            <p><code>gvim</code></p>
        </div>
    </div>





</div>

<div class="container gray padding40">
    <div class="row">
        <div class="threecol">
            <h3>Normal Mode</h3>
            <p> When vim starts up, you are in this mode. It is also known as the Command mode.</p>
        </div>
        <div class="threecol">
            <h3>Visual Mode</h3>
            <p>This is much like the normal mode but you can specify the areas to highlight in the editor and can issue commands against those selections.</p>
        </div>
        <div class="threecol">
            <h3>Insert Mode</h3>
            <p>
                The type entered in this mode will be part of the document.
            </p>
        </div>
        <div class="threecol last">
            <h3>Command Line Mode</h3>
            <p>In this mode, we can enter one line of text (command) at the bottom of the window.
        </div>
    </div>
</div>


<div class="container padding40">
    <div class="row">
        <h2>Preparing the stage with Pathogen</h2>
        <div class="eightcol">
            <p class="para">The strength of vim is its plugins and managing them manually will be cumbersome at the least, here comes pathogen to the rescue.
            Go to your VimFiles directory inside the Vim installation folder (example: C:\Program Files\Vim\vimfiles) and copy pathogen's Autoload directory</p>
<pre>
    https://github.com/tpope/vim-pathogen
</pre>
            <p> Open your vimrc file for configuration by issuing <code>:e $MYVIMRC</code> in vim normal mode and paste the following pathogen configuration at the top </p>

<pre>
    call pathogen#infect()
    syntax on
    filetype plugin indent on
</pre>


<p class="para">Issue <code>:w</code> to save those changes in the vimrc file and <code>:source $MYVIMRC</code> to load the changes from vimrc file without quiting vim. Because of the above default
configuration, pathogen will infect a directory called <code>bundle</code> inside the VimFiles folder and we are free to add vim plugins to bundle directory without worrying much. </p>

        </div>


        <div class="fourcol last right-align">
            <a href="https://github.com/tpope/vim-pathogen">Download Pathogen</a>
            <p><code>:e</code> command opens a file for editing</p>
            <p><code>$MYVIMRC</code> variable stores the path to vimrc file</p>
            <p>So <code>:e $MYVIMRC</code> opens your vimrc file for editing</p>
            <p><code>:source $MYVIMRC</code> re-loads the changed vimrc file</p>
            <p>Pathogen infects <code>bundle</code> folder by default</p>
            <p>Vim plugins may be placed in to <code>bundle</code> folder</p>
        </div>



    </div>
</div>

<div class="container padding40">
    <div class="row">
        <h2>Solarizing the Vim</h2>

        <div class="eightcol">
            <p class="para">The default color theme(s) in vim are very basic and bland. Thanks to the vim's plugin architecture we can customize the look however we want.
            Create and <code>cd</code> to your bundle directory (example: C:\Program Files\Vim\vimfiles\bundle) and clone the vim-colors-solarized color scheme by issuing 
            <code>git clone git://github.com/altercation/vim-colors-solarized.git</code>.</p>. Add the following to your vimrc file.

<pre>
    syntax enable
    set background=light
    colorscheme solarized
</pre>
            
            
            <p> Restart vim and the new color scheme will be applied to the vim.</p>

            <p class="para">There is a couple of things to be taken care of, like font size and tab indentation. Add <code>set guifont=Consolas:h11:cANSI</code> to your vimrc file and reload it (make sure Consolas is available in your system or use another available font). Vim has four variables that helps in fine tuning the tab space and are illustrated below. . Add the following configuration to vimrc file and restart vim to make sure the settings are applied. </p>
<pre>
    :set tabstop=4
    :set softtabstop=4
    :set shiftwidth=4
    :set expandtab
</pre>


        </div>

    <div class="fourcol last right-align">
            <a href="https://github.com/altercation/vim-colors-solarized">Download Solarized Color Scheme</a>
            <p>Solarized also has a dark color scheme, that can be activated by <code>set background=dark</code> in vimrc</p>
    </div>


    </div>


    


</div>


<div class="container padding40 gray">
    <div class="row">
        
        <div class="threecol">
            <h3>expandtab</h3>
            <p>When this is enabled, vim uses space instead of tab character. This is a boolean attribute. This will not affect the 
                existing tab characters (:retab to do that)</p>



        </div>      

        <div class="threecol">
            <h3>tabstop</h3>
            <p>This setting controls the number of space characters inserted when the tab is pressed.</p>
        </div>

        <div class="threecol">
            <h3>shiftwidth</h3>
            <p>This determines the amount of whitespace to be inserted for indentation</p>
        </div>

        <div class="threecol last">
             <h3>softtabstop</h3>
            <p>This is usually set as same value of tabstop</p>
        </div>

    
    </div>
</div>



<div class="container padding40">
    <div class="row">
        <h3>Supercharging HTML and CSS coding through ZenCoding</h3>

        <div class="eightcol">
        Zen coding makes writing markup a breeze. Clone Zen coding plugin into your pathogen infected bundle folder.
         <pre>git clone git://github.com/mattn/zencoding-vim.git</pre>

        <p class="para">Restart Vim and make sure that zen coding plugin is in the bundle directory. In insert mode enter <code>html:5</code> and press CTRL-y and comma(,). If everything goes fine zen coder should have expanded that snippet to a full blown html5 structure including doctype, head, and body.</p>

        </div>

   
        
        

      <div class="fourcol last right-align">
           <p> <a href="http://mattn.github.com/zencoding-vim/">Download Zen coding plugin</a></p>
    <p>
    	<code>CTRL-y + ,</code> is the shortcut for Zen coding plugin
    </p>
    </div>



    </div>



    <div class="container">
    	<div class="row padding40">
    	<h3>NERDTree as File  Explorer</h3>
    		<div class="eightcol">
    		
                <p class="para">
                    NERDTree gives functionality to vim like file opening, hierarchical folder navigation, and bookmarking. Install it in the bundle folder.
                </p>

<pre>
    git clone git://github.com/scrooloose/nerdtree.git
</pre>

                <p class="para">
                Restart Vim and we can explore NERDTree. Enter <code>:NERDTree</code> in command line mode and NERDTree opens as a split. Arrow keys or Vim navigational keys <kbd>h</kbd><kbd>j</kbd><kbd>k</kbd><kbd>l</kbd> could be used for moving around the hierarchy. <kbd>o</kbd> can be used for expanding the folder or opening the file as new split depending on whether the cursor is on folder or a file. Open a file in a tab by moving the cursor to that file name and pressing the key <kbd>t</kbd>. Another useful key is <kbd>p</kbd> for navigating to the root folder, when the cursor is on child folder. You can use <kbd>go</kbd> for previewing the selected file instead of opening it for editing.
                </p>
    		</div>
        

        <div class="fourcol last right-align">
            <a href="https://github.com/scrooloose/nerdtree">Download NERDTree</a>
            <p class="para"><code>CTRL-w</code> can be used for moving the cursor between the NERDTree and file windows or splits</p>
        </div>
    	</div>
    </div>



    <div class="container padding40">
    	<div class="row">
    		<h3>Surround Plugin</h3>

            <div class="eightcol">
            
                <p class="para">This plugin provides mappings to easily delete, change and add such surroundings in pairs. Install the plugin in the bundle folder using the following command</p>
                <code>git clone git://github.com/tpope/vim-surround.git</code>

                <p>In visual mode (charcter or line wise) make a selection around the text that should be surrounded, press <kbd>S</kbd> and then enter the the tag or character to use for surrounding followed by pressing the <kbd>ENTER</kbd> key.</p>
                <table class="zebra-striped">
                	<thead>
                		<tr>
                			<th>Command</th>
                			<th>Meaning</th>
                		</tr>

                        
                	</thead>

                    <tbody>
                    	<tr>
                    		<td>ds</td>
                    		<td>Given a character target to delete, it deletes that surrounding</td>
                    	</tr>
                    	<tr>
                    		<td>cs</td>
                    		<td>Replaces the target surrounding with the given replacement. <code>t</code> will act as placeholder for the tag</td>
                    	</tr>
                    	<tr>
                    		<td>ys</td>
                    		<td>Takes a valid vim motion and wraps it using the second argument</td>
                    	</tr>
                    	<tr>
                    		<td></td>
                    		<td></td>
                    	</tr>
                    </tbody>
                </table>


            </div>
            <div class="fourcol right-align last">
            	<a href="https://github.com/tpope/vim-surround">Install Surround Plugin</a>
            </div>


    	</div>
    </div>


    <div class="container padding40">
    	<div class="row">
    		<h2>Folding</h2>
            <div class="eightcol"><p class="para">Vim can fold blocks of code.
            Select the lines to be folded in vim (for example, using the line
            wise visual mode) and then press <kbd>z</kbd><kbd>f</kbd> keys to
            make it folded. You can open the fold using
            <kbd>z</kbd><kbd>o</kbd> and to close it back press
            <kbd>z</kbd><kbd>c</kbd></p></div>
            <div class="fourcol right-align last"></div>
    	</div>
    </div>


<div class="container padding40">
	<div class="row">
		<h2>Creating KeyBoard Shortcuts</h2>
		<div class="eightcol">
        <p class="para">
            The easiest way to understand creating a shortcut, is well, by creating it. Let's map the <kbd>Space</kbd> in normal mode to <kbd>PageDown</kbd>. Issue the following command.

            <pre>
                :nmap &lt;Space&gt; &lt;PageDown&gt;
            </pre>

            
        
        </p>
        </div>
		<div class="fourcol right-align last"></div>
	</div>
</div>

    

  <div class="container padding40">
  	<div class="row">
      <h2>Tips & Tricks</h2>
  		<div class="eightcol">
        <p class="para">
          <kbd>c</kbd><kbd>i</kbd>group of commands could be useful for
          changing the inner contents. For example to change the content inside
          a heading in html like <code>&lt;h1&gt;change me&lt;/h1&gt;</code>,
          place the cursor anywhere over "change me" and then press cit and
          type your new heading. <kbd>c</kbd><kbd>i</kbd><kbd>w</kbd>,
          <kbd>c</kbd><kbd>i</kbd><kbd>'</kbd>, and
          <kbd>c</kbd><kbd>i</kbd><kbd>t</kbd> changes the inner content of a
          word, quoted phrase, and tags respectively. 
        </p>

        <p class="para">Enable and disable spell checking by issuing the
        commands <code>:set spell </code>and <code>:set nospell </code>
        respectively. <kbd>z</kbd><kbd>=</kbd> can be used to list (and use)
        the spelling suggestions when the cursor is above a wrong word.
        </p>



        <p class="para">
          When the cusror is over a word you may search for that word above or below that one using the commands <kbd>*</kbd> and <kbd>#</kbd>.
        </p>


        <p class="para">
          <code>:r</code> is used to read the contents (like from file or command line) in to the buffer / file. If it is provided with a file name it inserts the contents of that file into the file. The following snippet inserts the date into the file.
        </p>

<pre>
:r !date /t
</pre>



        <p class="para">
          <kbd>CTRL</kbd>+<kbd>o</kbd> and <kbd>CTRL</kbd>+<kbd>i</kbd> moves you from and to where the cursor has been.
        </p>

        <p class="para">
          Use :bd to close the buffer / file without quiting vim itself. <kbd>CTRL</kbd>+<kbd>[</kbd> is equivalent to pressing <kbd>ESC</kbd> in vim.
        </p>

      <p class="para">
        Using "u" and CTRL-R will not get you to all possible text states
  while repeating <kbd>g</kbd><kbd>-</kbd> and <kbd>g</kbd><kbd>+</kbd> does.
      </p>

      <p class="para">
        If you're working in insert mode, you can change the indent level of the current line using <kbd>CTRL </kbd> <kbd>t </kbd> and <kbd>CTRL </kbd> <kbd>d</kbd>. These commands work no matter where your cursor is positioned on the current line and adjust the indent level based on your shiftwidth setting.
  
      </p>

      <p class="para">
        In insert mode if you hit <kbd>CTRL</kbd><kbd>o</kbd> Vim will accept one normal mode command and brings back you to insert mode. A lifesaver. Example <kbd>CTRL</kbd><kbd>o</kbd> <kbd>g</kbd><kbd>q</kbd><kbd>l</kbd> -> format current line and carry on the typing.
      </p>



        <p class="para">
          Wrapping for long lines is on by default and the movement keys will move based on the logical lines instead of screen lines. For moving through the screen lines prepend <kbd>g</kbd> like "gj".
        </p>

        <p class="para">
            <kbd>g</kbd><kbd>f</kbd> is a mnemonic for go to file and it opens the file name under the cursor.
        </p>

      </div>


  	</div>
  </div>









    <div class="container padding40">
    	<div class="row">
        <h3>Commands Reference - level A</h3>

        <div class="eightcol">
            <table class="zebra-striped">
                <thead>
                    <tr>
                    	<th>Command</th>
                    	<th>Meaning</th>
                    </tr>
                </thead>
            	<tr>
            		<td><code>i</code></td>
            		<td>Switch to insert mode inside command mode</td>
            	</tr>
            	<tr>
            		<td>h,j,k,l</td>
            		<td>Moving around aka Arrow keys</td>
            	</tr>
            	<tr>
            		<td>x</td>
            		<td>Delete charcater. Think of good old days of typewriter when deletion is typing x over the characters </td>
            	</tr>
            	<tr>
            		<td>u, CTRL-r</td>
            		<td>Undo and Redo respectively. Capitalize u (U) to undo the changes in a line.</td>
            	</tr>
            	<tr>
            		<td>zz</td>
            		<td>In command mode, writes the file and exit. :w commits the changes without exiting.</td>
            	</tr>

                <tr>
                	<td>:q!</td>
                	<td>Enter command line mode, quit the editor, and force quitting by discarding the changes. :q is the safe version</td>
                </tr>

                <tr>
                	<td>i and a</td>
                	<td>i inserts before the cursor and a after the cursor</td>
                </tr>

                <tr>
                	<td>o</td>
                	<td>Open up a new line before the cursor. Capitalize (O) to open a line above cusror.</td>
                </tr>

            </table>
        </div>
        
        <div class="fourcol right-align last">
            <p class="para">
                Precede a number with the movement commands for repeating it that times. For example 3x deletes three charaacter and 8j moves the cursor to eight lines downward.
            </p>
        </div>

        </div>
    </div>










    <div class="container padding40">
    	<div class="row">
            <h3>Commands Reference - Level B</h3>
    		<div class="eightcol">
                <table class="zebra-striped">
                	<thead>
                		<tr>
                			<th>Command</th>
                			<th>Meaning</th>
                		</tr>
                	</thead>

                    <tbody>
                        <tr>
                        	<td>w,b</td>
                        	<td>Word movement; w moves the cursor forward one word and b moves it backwards</td>
                        </tr>
                        <tr>
                        	<td>$,0,^</td>
                        	<td>$ moves the cursor to the end of line, 0 to the beginning and ^ to the first character of line.</td>
                        </tr>
                        <tr>
                        	<td>f,t</td>
                        	<td>Searches along a single line. Capitalize (F) to search backwards. t is similar but stops one character before the searched one and (T) is the backwards version </td>
                        </tr>
                        <tr>
                        	<td>G</td>
                        	<td>With no argument, it positions cursor on the last line. Specify a number as argument (like 10G) to position on that line</td>
                        </tr>
                        <tr>
                        	<td>CTRL-u, CTRL-d</td>
                        	<td>Scrolls up and down respectively.</td>
                        </tr>
                        <tr>
                        	<td>dd,dw,d[movement]</td>
                        	<td>dd deletes a line, dw deletes a word and d[movement] deletes up to where the movement command ends up. For example d4w deletes four words</td>
                        </tr>


                        <tr>
                        	<td>c</td>
                        	<td>Changes a word. For example cw deletes a word and places the cursor for entering the new word in its place.</td>
                        </tr>
                        <tr>
                        	<td>.</td>
                        	<td>Repeats the last executed command</td>
                        </tr>
                        <tr>
                        	<td>r</td>
                        	<td>Replaces the character under the cursor</td>
                        </tr>
                        <tr>
                        	<td>~</td>
                        	<td>Changes the case of the charecter under the cusror</td>
                        </tr>
                        <tr>
                        	<td>CTRL-k [digraph code]</td>
                        	<td>For inserting the characters not in the keyboard. For example CTRL-kCt inserts a cent(&cent;) character</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
        <div class="fourcol right-align last">
            Escape key aborts most commands
            <p><code>:set number</code> displays the number on left margin. <code>:set nonumber</code> turns it off</p>
            <p><code>:digraphs</code> for listing the available special characters</p>
        </div>


    	</div>
    </div>




    <div class="container padding40">
    	<div class="row">
    		<h3>Commands Reference - Level C</h3>
            <div class="eightcol">
                <table class="zebra-striped">
                	<thead>
                		<tr>
                			<th>Command</th>
                			<th>Meaning</th>
                		</tr>
                	</thead>
                    <tbody>
                    	<tr>
                    		<td>/[search pattern],?[search pattern]</td>
                    		<td>searches the document for the given pattern for example /one will search for the word one after you press ENTER. n and N can be used for navigating the search results. ? reverses the search.</td>
                    	</tr>
                    	<tr>
                    		<td>p</td>
                    		<td>Puts the character(s) in the register after the cursor.</td>
                    	</tr>
                    	<tr>
                    		<td>m[a-z], `[a-z], '[a-z]</td>
                    		<td>ma creates a mark called a. You can navigate to that line of mark using `a and to exact location by using 'a</td>
                    	</tr>
                    	<tr>
                    		<td>y,Y</td>
                    		<td>Yanks or copies a character in to register. Capitalized (Y) copies the entire line</td>
                    	</tr>
                        <tr>
                        	<td>!, !!</td>
                        	<td>Filtering operator. Expects a motion command to select the area to filter and sends it to external programs. !! runs the current line through filter. Examples <code>!!date</code> and <code>!!dir</code></td>

                        </tr>
                        <tr>
                        	<td>:e [file], :view [file]</td>
                        	<td>Edit another file. :view opens file in read only mode.</td>
                        </tr>
                        <tr>
                        	<td>:next, :previous, :first, :last</td>
                        	<td>Cycle through the files opened for editing</td>
                        </tr>
                        <tr>
                        	<td>:split, :split [file], :new, :sview</td>
                        	<td>Splits the current file in to two windows and places the cursor on top one. Optional file attribute specifies which file to open in the new window. :new splits but without loading the current file.:sview opens the window in read only mode.</td>
                        </tr>
                        <tr>
                        	<td>CTRL-w, CTRL-wj, CTRL-wk</td>
                        	<td>CTRL-w to cycle through the windows and the rest of the meaning you could guess from the letters k and j</td>
                        </tr>
                        <tr>
                        	<td>CTRL-w+, CTRL-w-, CTRL-w=</td>
                        	<td>Increases, decreases, and makes equal size windows respectively.</td>
                        </tr>
                        <tr>
                        	<td>:hide</td>
                        	<td>Hides the current buffer from the screen.</td>
                        </tr>
                        <tr>
	                        <td>:buffers</td>
	                        <td>List the buffers / files</td>
                        </tr>
                        <tr>
                        	<td>:buffer [number], :buffer [file], :sbuffer</td>
                        	<td>Activates the buffer for editing by number or file name. :sbuffer opens the buffer in a new window</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <div class="fourcol right-align last">
                <code>:nohlsearch</code> removes the highlighting of the current search pattern.
                <p><code>:set hlsearch</code> is the boolean attribute that controls search high lighting </p>
                <p><code>:set incsaerch</code> activates the incremental search</p>
<p>Vim register maintains the character(s) you have copied / deleted. Capitalized (P) places character before the cursor.</p>
<p><code>:marks</code> lists all the marks created</p>
<p>Vim uses the term buffer to refer to the file being edited</p>   
            </div>
    	</div>


    <div class="container">
    	<div class="row padding40">
    		<h3>Commands Reference - Level D</h3>
            <div class="eightcol">
                <table class="zebra-striped">
                	<thead>
                		<tr> <th>Command</th> <th>Meaning</th> </tr>
                	</thead>

                    <tbody> 
                        <tr>
                            <td>v,V,CTRL-Q</td>
                            <td>Starts character, line, and block visual modes respectively</td>
                        </tr>
                        <tr>
                        	<td>J</td>
                        	<td>Used to join the highlighted lines to single line separated by space</td>
                        </tr>
                        <tr>
                        	<td>>,<</td>
                        	<td>Intends the selected lines forwards and backwards respectively</td>
                        </tr>
                        <tr>
                        	<td>I,c,A,r,>,<</td>
                            <td>In visual block mode, inserts the specified string on the left side of selection. Press ESC after entering the text to be inserted instead of ENTER. c changes the selection. A appends the text. r replaces the character. < and > shifts the selection. </td>


            
                        </tr>
                        <tr>
                            <td><<, >></td>
                        	<td>In command mode, it shifts the line backwards and forwards respectively</td>
                        </tr>


                        <tr>
                        	<td>:abbreviate</td>
                        	<td>Lists the abbreviation if no arguments given. Create an abbreviation for the original phrase. :abbreviate ad advertisement</td>
                            
                        </tr>
                        <tr>
                        	<td>:map</td>
                        	<td>Map a set of commands to a key. If no arguments given, it will list the maps.</td>
                        </tr>


                            
                        
                    </tbody>
                </table>
            </div>
    	</div>
    </div>






    </div>




</div>


<div class="container padding40">
	<div class="row">
		<h2>References</h2>
		<div class="sixcol">
      <p>
        http://dailyvim.blogspot.com
      </p>

      <p>
        http://vim.runpaint.org/toc/
      </p>
    </div>
		<div class="sixcol last"></div>
	</div>
</div>



