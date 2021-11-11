all: slides-meetechofixed.pdf

slides.pdf: slides.tex pinata-nobackground.pdf balloon-nobackground.pdf film-spool-nobackground.pdf
	lualatex $<

pinata.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/delapouite/pinata.svg -O $@

balloon.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/lorc/balloons.svg -O $@

film-spool.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/delapouite/film-spool.svg -O $@

%-nobackground.svg: %.svg
	sed 's/<path fill="#fff" d="M0 0h512v512H0z".>//' < $< > $@

%.pdf: %.svg
	inkscape $< -o $@

%-meetechofixed.pdf: %.pdf
	pdfjam --suffix meetechofixed --papersize "{1600mm,900mm}" $<
