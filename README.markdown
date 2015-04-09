# Pandoc Configuration and Support Files

Thanks to @kjhealy for writing this in the first place. I have forked and made modest changes.

I encourage you to [see his repo](https://github.com/kjhealy/pandoc-templates) for more detailed explanation of how this works. All that I am doing here is writing a note to myself so I remember how to set this up again.

## Setup process

1. `git clone git@github.com:spencerlyon2/pandoc-templates.git`
2. (Optional) Edit `makefile/Makefile` (in the pandoc-templates directory you just cloned) so that `BIB` points to your global latex `.bib` file. Then uncomment that line in the Makefile Notice that I did not do this. Instead, what I do is set the `bibliography` metadata field in my yaml metadata block.
2. `rm -rf ~/.pandoc` -- WARNING this is destructive. Only do this if you are very sure there is nothing you wish to keep in `~/.pandoc`
3. `mv pandoc-templates ~/.pandoc`
4. `git clone https://github.com/kjhealy/latex-custom-kjh`
5. `mv latex-custom-kjh ~/Library/texmf/tex/latex/local` (I swapped out `mv` with `ln -s` because I keep it somewhere else...). NOTE: this is an OSX only step. For other systems you will need to find where to store custom latex sty and cls files. Also, on OSX, some parent folders of `~/Library/texmf/tex/latex/local` may not exist. If that is the case this step will fail. Simply create them as blank directories (`mdkir -p ~/Library/texmf/tex/latex/local` then repeat the `mv` command)
6. (Optional) copy the Makefile to the working directory of your project for easy pandoc compilation `cp ~/.pandoc/makefile/Makefile path/to/project`
7. (Optional) Install the sublime MakeCommands package for easy compilation (using the makefile you just copied) from within sublime.
8. Enjoy
