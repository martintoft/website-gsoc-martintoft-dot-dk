This is a collection of patches for Vim 7.1 sent to Bram Moolenaar (bram at
moolenaar dot net) by Martin Toft Bay (mt at martintoft dot dk) during Google
Summer of Code 2007. Most of the patches have been committed to the official
repository and the rest is on the way, either as patches for 7.1 or simply as
patched files in 7.2.

Relevant web addresses:

    Google Summer of Code 2007
    http://code.google.com/soc/2007

    Vim
    http://www.vim.org

    Vim 7.1 patch directory
    ftp://ftp.vim.org/pub/vim/patches/7.1

The "Fix bugs" project idea from http://www.vim.org/soc/ideas.php:

    Vim has many, many features. We don't really need more, we do need the
    existing features to work reliably and predictably.

    The todo list has many issues that Vim users reported. See ":help todo" or
    this link. These need to be sorted out and when it's a real bug it must be
    fixed. Or perhaps the help text need to be adjusted. Some changes may
    require discussing the solutions on the vim-dev maillist.

    This can be worked on by more than one person. 

My application abstract from
http://code.google.com/soc/2007/vim/appinfo.html?csaid=9E132DFEDA0517AF:

    The many features of Vim makes it a really great editor, however, as the
    list of features grow, it is important to keep all of them working
    flawlessly. Users trust Vim when editing even their most important files
    and must be spared as many unpleasant surprises as possible. I have chosen
    14 known bugs to focus on and categorised them into "General Bugs", "Syntax
    Highlighting Bugs", "Completion Bugs", and "Documentation Bugs". The
    general bugs that I wish to fix are:

      - When setting 'keymap' twice the b:keymap_name variable isn't set.
	(Milan Berta, 2007 Mar 9) Has something to do with 'iminsert'.
      - ":lockvar" should use copyID to avoid endless loop.
      - More-prompt is skipped when doing this; (Randall W. Morris, Jun 17)
          :au
          <Space>
          b
          <Space>
      - ":confirm w" does give a prompt when 'readonly' is set, but not when
	the file permissions are read-only. Both can be overruled by ":w!" thus
	it would be logical to get a prompt for both. (Michael Schaap)
      - When 'bomb' is set or reset the file should be considered modified.
	(Tony Mechelynck) Handle like 'endofline'.
      - ":py" asks for an argument, ":py asd" then gives the error that ":py"
	isn't implemented. Should already happen for ":py".
      - Allow more than 3 ":match" items.
      - When pattern for ":sort" is empty, use last search pattern. Allows
	trying out the pattern first. (Brian McKee)

    Syntax highlighting bugs:

      - C syntax: "#define x {" The macro should terminate at the end of the
	line, not continue in the next line. (Kelvin Lee, 2006 May 24)
      - C syntax: {} inside () causes following {} to be highlighted as error.
	(Michalis Giannakidis, 2006 Jun 1)

    Completion bugs:

      - C completion: doesn't work after aa[0]->, where aa is an array of
	structures. (W. de Hoog, 2006 Aug 12)
      - Completion menu: For a wrapping line, completing a long file name, only
	the start of the path is shown in the menu. Should move the menu to the
	right to show more text of the completions. Shorten the items that
	don't fit in the middle?

    Documentation bugs:

      - Write "making vim work better" for the docs (mostly pointers): *nice*
        - sourcing $VIMRUNTIME/vimrc_example.vim
        - setting 'mouse' to "a"
        - getting colors in xterm
        - compiling Vim with X11, GUI, etc.
      - There should be something about spell checking in the user manual.

    Some of the bug descriptions are vague and will need to be discussed with
    developers and bug reporters.

As hinted in my full application, the bugs on the list were merely suggestions.
Here is the snippet:

    If you do not like the bugs that I have chosen, I am certainly willing to
    do other bug fixing tasks that you deem more important.

Most of the list's bugs have been fixed (or at least "attacked" in an attempt
to fix them), but after getting more familiar with Vim's todo.txt I dropped
some of the list's bugs and instead chose to work on other bugs that I found
more important or interesting.

Thanks to Bram Moolenaar for great feedback and for his incredible patience
with a newcomer like me.

Also, thanks for Chris Lubinski (cmc333333 at gmail dot com) for help and
support.  He worked on bug fixing too.

Sincerely,
Martin Toft Bay,
Denmark, 2007 August 20.
