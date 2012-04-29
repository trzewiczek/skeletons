STATICS = _site/static
CSS_IN  = $(STATICS)/css/style.css
CSS_OUT = $(STATICS)/css/style.min.css
SOURCE  = _site/*

test: 
	jekyll --server

publish: $(CSS_IN) $(SOURCE)
	jekyll --no-auto
	yui-compressor $(CSS_IN) -o $(CSS_OUT)
	rm $(CSS_IN)
	rsync -v -r -e ssh $(SOURCE) jekyll@scaffold.rb:~/public_html/Jekyll_Scaffold

.PHONY:	run
