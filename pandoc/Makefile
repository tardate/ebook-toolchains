include_dir=include
css_dir=stylesheets
out_dir=build
image_dir=../content/images
source=../content/chapters/*.m*d*
title='eBook Toolchains'
filename='ebook-toolchains'

all: html epub rtf pdf

epub:
	pandoc -s $(source) --normalize --smart -t epub -o $(out_dir)/$(filename).epub \
		--epub-metadata $(include_dir)/metadata.xml \
		--epub-stylesheet $(css_dir)/epub.css \
		--epub-cover-image $(image_dir)/cover.png \
		--title-prefix $(title) \
		--normalize \
		--smart \
		--toc

html:
	pandoc -s $(source) -t html5 -o $(out_dir)/$(filename).html -c $(css_dir)/style.css \
		--include-in-header $(include_dir)/head.html \
		--include-before-body $(include_dir)/header.html \
		--include-before-body $(include_dir)/share.html \
		--include-after-body $(include_dir)/footer.html \
		--title-prefix $(title) \
		--normalize \
		--smart \
		--toc

rtf:
	pandoc -s $(source) -o $(out_dir)/$(filename).rtf \
		--title-prefix $(title) \
		--normalize \
		--smart

pdf:
	# You need `pdflatex`
	# OS X: http://www.tug.org/mactex/
	# Then find its path: find /usr/ -name "pdflatex"
	# Then symlink it: ln -s /path/to/pdflatex /usr/local/bin
	pandoc -s $(source) -o $(out_dir)/$(filename).pdf \
		--title-prefix $(title) \
		--normalize \
		--smart \
		--toc