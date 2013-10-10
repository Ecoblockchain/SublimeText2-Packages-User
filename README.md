# Sublime Text 2 - Personal Config / Style Guides

----------

## Setting Up My IDE (Sublime Text 2) 

### Prerequisites 
 1. Install [Sublime Text 2][1]
 2. Install [Sublime Package Control][2]

### Install Recommended Packages

 1. Type **⌘⇧P** *(Command+Shift+P)* in **Sublime Text** to open the **Command Palette**.
 2. Type **Install Package** to open **Package Control: Install Package**.
 3. Install these packages:
  - **CSSComb** *(Tool for sorting CSS properties in specific order)*
  - **JSFormat** *(Javascript formatting for Sublime Text 2)*
  - **SASS** *(SASS support for TextMate & Sublime Text 2)*
  - **SideBarEnhancements** *(Enhancements to Sublime Text sidebar. Files and folders.)*
  - **SublimeLinter** *(Inline lint highlighting for the Sublime Text 2 editor)*

### Clone Package Settings
1. Open **Terminal** and navigate to the **Sublime Text 2** settings directory.

        cd ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/

2. Clone the repository.

        git clone https://github.com/lvtech/resources-feds.git "User"

### Usage

- To run JSFormat, press Control+Alt+F.
- To run CSSComb, press Control+Shift+C. CSSComb works with SASS files.

----------

----------

## JavaScript Style Guide
Our JavaScript style guide is based on the [Google JavaScript Style Guide][3]. 

The first half of Google's document, **JavaScript Language Rules**, is for reading on your own. 

These are our overrides to the **JavaScript Style Rules** section of the Google guide:

 - **Naming**: Use .'s and _.'s in filenames if it makes a filename easier to read.

  **No**

        touch FinancialInbox.js
    
  **Yes**

        touch Financial_Inbox.js

 - **Custom toString() methods**: Just don't do this, unless you REALLY have to.

 - **Code Formatting**: Use **JSFormat**.

 - **Avoid returning anonymous functions**: Store them in a variable and return that. It's easier to debug.

 - **Try to wrap lines at 80 characters**. It's easier to read.

 - **Use $ in front of variable names for jQuery selectors**. You should be caching them. Also, chain your calls.

  **No**

        $('.cool-section').addClass('active');
        $('.cool-section').fadeIn(400);
        $('.cool-section').fadeOut(400);
        $('.cool-section').removeClass('active');
     
  **Yes**

        var $coolSection = $('.cool-section');
        $coolSection.addClass('active')
        	.fadeIn(400)
        	.fadeOut(400)
        	.removeClass('active');

 - **Loops** In order of preference (based on complexity):
  1. Underscore.js functions like underscore.each()
  2. jQuery.each() or jQuery.map()
  3. for (var i = 0; i < whatever.length; i++) {}

 ### Bottom Line
 - Code your own way (responsibly), but use **JSFormat** before checking in a file. 
 - To run **JSFormat**, press Control+Alt+F.
 - If you work on a file that has not been formatted, use **JSFormat** before you check it back in.

----------

## PHP Style Guide

Our PHP style guide is based on the [WordPress Core PHP Coding Standards][4]. 

These are our overrides to the WordPress guide:

 - **Brace Style**: Use braces with any blocks of if/else logic, even with single line blocks.

   **No**

        if ( condition )
            action1();
        elseif ( condition2 )
            action2();
        else
            action3();
        
   **Yes**

        if ( condition ) {
            action1();
        } elseif ( condition2 ) {
            action2();
        } else {
            action3();
        }

 - **Space Usage**: No space is necessary when testing false between a ! and a variable.

   **No**

        if ( ! $foo ) { ...

   **Yes**

        if ( !$foo ) { ...

 - **Naming Conventions**: Use camelCase for method declarations.

   **No**

        function some_name( $some_variable ) { [...] }

   **Yes**

        function someName( $some_variable ) { [...] }        

 - **Yoda Conditions**: Ignore this rule, but understand the issue that is avoided by using Yoda conditions. Regardless, they are not easy to read, and you should be using === anyway, or at the very least, ==.

   **No**

        if ( true == $the_force ) {
            $victorious = you_will( $be );
        } 

   **Yes**

        if ( $the_force === true ) {
            $victorious = youWill( $be );
        } 

 - **Clever Code**: Ignore this. One line if/else clauses are fine.

   **Yes**

        isset( $var ) || $var = some_function();
    
   **Also Yes**

        if ( !isset( $var ) ) {
            $var = some_function();
        }
    
----------

  [1]: http://www.sublimetext.com/
  [2]: http://wbond.net/sublime_packages/package_control
  [3]: http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml
  [4]: http://make.wordpress.org/core/handbook/coding-standards/php/