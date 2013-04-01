FILE=lec10-lan
#FILE=lec09-link
#FILE=lec08-secure
#FILE=lec07-route
#FILE=lec06-network
#FILE=lec05-socket
#FILE=lec04-transport
#FILE=lec03-rely
#FILE=lec02-app
#FILE=lec01-intro
POST_FILE=$(FILE)-post
SHOW_FILE=$(FILE)-show

all: $(POST_FILE).pdf $(SHOW_FILE).pdf

$(POST_FILE).pdf: $(POST_FILE).tex $(FILE).tex lib/header.tex
	xelatex $(POST_FILE).tex
#	xelatex $(POST_FILE).tex

$(SHOW_FILE).pdf: $(SHOW_FILE).tex $(FILE).tex
	xelatex $(SHOW_FILE).tex
#	xelatex $(SHOW_FILE).tex

post:
	bash upload.sh $(POST_FILE).pdf $(FILE).pdf
	
convert:
	open -a "PDF to Keynote" $(SHOW_FILE).pdf

clean:
	rm $(POST_FILE).aux $(POST_FILE).log $(POST_FILE).toc $(POST_FILE).pdf $(POST_FILE).snm $(POST_FILE).nav $(POST_FILE).out $(POST_FILE).vrb
	rm $(SHOW_FILE).aux $(SHOW_FILE).log $(SHOW_FILE).toc $(SHOW_FILE).pdf $(SHOW_FILE).snm $(SHOW_FILE).nav $(SHOW_FILE).out $(SHOW_FILE).vrb

mrproper:
	rm *.aux *.log *.toc *.pdf *.snm *.nav *.out *.vrb
