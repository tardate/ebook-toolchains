include_dir=include
css_dir=stylesheets
out_dir=build
image_dir=images
source=chapters/index.md
title='eBook Toolchains'
filename='ebook-toolchains'

all: html epub rtf

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
