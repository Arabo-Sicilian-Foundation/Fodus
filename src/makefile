# Mettre ici vos options de compilation.
#
CFLAGS= -DDEBUG -g -Wall `pkg-config --cflags MLV`

#
# Mettre ici les options qui devront être passées à l'éditeur de liens.
# Par exemple : -L/directory
#
LDFLAGS = `pkg-config --libs-only-other --libs-only-L MLV`

#
# Mettre ici les noms des bibliothèques et leurs locations.
# Par exemple : -lpthread
#
LDLIBS=`pkg-config --libs-only-l MLV`

########################################################################
#
# Pour compiler le latex
#
pdf: latex

latex: compte-rendu_Fodus.tex
	pdflatex compte-rendu_Fodus.tex

########################################################################
CC=gcc

fodus: main.o map.o personnage.o jeux.o sauvegarde.o ia.o menu.o knight.o marksman.o
	$(CC) main.o map.o personnage.o jeux.o sauvegarde.o ia.o menu.o knight.o marksman.o -o fodus $(LDFLAGS) $(LDLIBS)

marksman.o: marksman.c marksman.h
	$(CC) $(CFLAGS) -c marksman.c

knight.o: knight.c knight.h
	$(CC) $(CFLAGS) -c knight.c

map.o: map.c map.h
	$(CC) $(CFLAGS) -c map.c

personnage.o: personnage.c personnage.h
	$(CC) $(CFLAGS) -c personnage.c

jeux.o: jeux.c jeux.h
	$(CC) $(CFLAGS) -c jeux.c

sauvegarde.o: sauvegarde.c sauvegarde.h
	$(CC) $(CFLAGS) -c sauvegarde.c

ia.o: ia.c ia.h
	$(CC) $(CFLAGS) -c ia.c

menu.o: menu.c menu.h
	$(CC) $(CFLAGS) -c menu.c

main.o: main.c
	$(CC) $(CFLAGS) -c main.c

clean:
	rm -rf *.o *.~ fodus *.aux *.fdb_latexmk *.fls *.log *.synctex.gz *~ *.pdf *.out
