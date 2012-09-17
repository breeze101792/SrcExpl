**SrcExpl**
===========

SrcExpl is a source code explorer that provides context for the currently
selected keyword by displaying the function or type definition or declaration
in a separate window. This plugin aims to recreate the context window available
in the IDE known as "Source Insight".

Features
========

* Display definitions and declarations of various languages supported
      by ctags and various types including functions, macros, structures,
      arrays, methods, classes, and variables.
* Jump to the displayed context in the SrcExpl window using the mouse or
      your own key mapping.
* Jump back from the context location with the mouse context menu or your
      own key mapping.
* Automatically list all definitions if multiple definitions for a keyword
      is found.
* Automatically create and update the tags file.

Installation
============
1. Ensure ctags is installed on your system and that VIM can use it.
2. Place the SrcExpl files in your Vim directory (such as ~/.vim) 
   or have it installed by a bundle manager like Vundle or NeoBundle.
3. Open the SrcExpl window with *:SrcExpl* or *:SrcExplToggle* or map these
   commands to keys in your .vimrc.

Requirements
------------
SrcExpl requires:
* Vim 7.0 or higher
* ctags

Screenshots
===========

One Declaration Found
---------------------
![One Declaration Found](http://3.bp.blogspot.com/_-FHYidE7rhE/SLv9-eDUkdI/AAAAAAAAAA0/EWa0qhMln9A/s1600-h/One+definition.bmp)

Multiple Declarations Found
---------------------------
![Multiple Declarations Found](http://3.bp.blogspot.com/_-FHYidE7rhE/SLv-iX6MVBI/AAAAAAAAAA8/waxJKcy1V3M/s1600-h/Multiple+definitions.bmp)

Local Declaration Found
-----------------------
![Local Declaration Found](http://3.bp.blogspot.com/_-FHYidE7rhE/SLv_O5By32I/AAAAAAAAABE/Cw5yx2N29y0/s1600-h/Local+definition.bmp)

Settings Example
================
```vim
" // The switch of the Source Explorer 
nmap <F8> :SrcExplToggle<CR> 

" // Set the height of Source Explorer window 
let g:SrcExpl_winHeight = 8 

" // Set 100 ms for refreshing the Source Explorer 
let g:SrcExpl_refreshTime = 100 

" // Set "Enter" key to jump into the exact definition context 
" let g:SrcExpl_jumpKey = "<ENTER>" 

" // Set "Space" key for back from the definition context 
let g:SrcExpl_gobackKey = "<SPACE>" 

" // In order to Avoid conflicts, the Source Explorer should know what plugins 
" // are using buffers. And you need add their bufname into the list below 
" // according to the command ":buffers!" 
let g:SrcExpl_pluginList = [ 
        \ "__Tag_List__", 
        \ "_NERD_tree_", 
        \ "Source_Explorer" 
    \ ] 

" // Enable/Disable the local definition searching, and note that this is not 
" // guaranteed to work, the Source Explorer doesn't check the syntax for now. 
" // It only searches for a match with the keyword according to command 'gd' 
let g:SrcExpl_searchLocalDef = 1 

" // Do not let the Source Explorer update the tags file when opening 
let g:SrcExpl_isUpdateTags = 0 

" // Use 'Exuberant Ctags' with '--sort=foldcase -R .' or '-L cscope.files' to 
" //  create/update a tags file 
let g:SrcExpl_updateTagsCmd = "ctags --sort=foldcase -R ." 

" // Set "<F12>" key for updating the tags file artificially 
let g:SrcExpl_updateTagsKey = "<F12>" 
```

Changelog
=========
5.0
- Replaced use of preview window with a named buffer.
- Moved to github.
- Added documentation.