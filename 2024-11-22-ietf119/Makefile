all: slides-meetechofixed.pdf

slides.pdf: slides.tex teacher-nobackground.pdf pinata-nobackground.pdf film-spool-nobackground.pdf calendar-nobackground.pdf cricket-nobackground.pdf
	lualatex $<

# sorry, game-icons.net doesn't work on the ietf-v6ONLY network
pinata.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/delapouite/pinata.svg -O $@

balloon.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/lorc/balloons.svg -O $@

film-spool.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/delapouite/film-spool.svg -O $@

calendar.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/delapouite/calendar.svg -O $@

misdirection.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/delapouite/misdirection.svg -O $@

teacher.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/delapouite/teacher.svg -O $@

cricket.svg:
	wget https://game-icons.net/icons/000000/ffffff/1x1/delapouite/cricket.svg -O $@


%-nobackground.svg: %.svg
	sed 's/<path fill="#fff" d="M0 0h512v512H0z".>//' < $< > $@

%.pdf: %.svg
	inkscape $< -o $@

%-meetechofixed.pdf: %.pdf
	# Workaround for meetecho doing slides at fixed DPI rather than fixed
	# size in pixels
	#
	# Thanks Kurt Pfeifle at https://stackoverflow.com/a/7507511
	gs \
	 -o $@ \
	 -sDEVICE=pdfwrite \
	 -g16000x9000 \
	 -dFIXEDMEDIA \
	 -dPDFFitPage \
	 -dCompatibilityLevel=1.4 \
	  $<
