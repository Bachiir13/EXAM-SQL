# EXAM-SQL

QUESTION 1 : SELECT * FROM artiste WHERE annéeNaiss < 1950;

QUESTION 2 : SELECT * FROM film WHERE genre = 'Drame';

QUESTION 3 : SELECT * FROM artiste WHERE nom ='Willis'; SELECT * FROM `role` WHERE idActeur ='62';

QUESTION 4 : SELECT * FROM `bdd existante`.`artiste` WHERE `idArtiste` = 525

QUESTION 5 : SELECT * FROM notation WHERE IdFilm ='275';

QUESTION 6 : SELECT * FROM `role` WHERE nomRôle ='Chewbacca';

QUESTION 7 : 58 minutes pour vivre, Une Journée en enfer, Die Hard 4 : Retour en enfer, Piège de cristal 
SELECT * FROM role WHERE idActeur ='62';

QUESTION 8 : SELECT artiste.nom, artiste.prénom FROM artiste, role, film WHERE artiste.idArtiste = role.idActeur AND role.idFilm = film.idFilm AND film.titre = 'Sueurs froides';;
Stewart James
Novak Kim
Bel Geddes Barbara

QUESTION 9 : SELECT * FROM notation WHERE email ='anon0@afpa-zakademie.com';

QUESTION 10 : SELECT DISTINCT f.titre FROM film f, artiste r, role ro, artiste a WHERE f.idRéalisateur = r.idArtiste AND f.idFilm = ro.idFilm AND ro.idActeur = a.idArtiste AND r.nom = 'Burton' AND r.prénom = 'Tim' AND a.nom = 'Depp' AND a.prénom = 'Johnny';


QUESTION 11 : SELECT film.titre, role.nomRole
FROM film, artiste, role
WHERE artiste.idArtiste = role.idActeur
  AND role.idFilm = film.idFilm
  AND artiste.nom = 'Allen'
  AND artiste.prénom = 'Woody';

Match point, Scoop, Manhattan, Annie Hall, Alice, Intérieurs, Maris et femmes, Minuit à Paris. Il a jouer comme role : Sid Waterman,Isaac Davis,Alvy Singer,Prof. Gabriel 'Gabe' Roth

QUESTION 12 : 

QUESTION 13 : SELECT f.titre FROM film f JOIN artiste a ON f.idRéalisateur = a.idArtiste WHERE a.nom = 'Tarantino' AND a.prénom = 'Quentin' AND f.idFilm NOT IN ( SELECT r.idFilm FROM role r WHERE r.idActeur = a.idArtiste );
Kill Bill : Volume 1
Jackie Brown
Kill Bill : Volume 2
Inglourious Basterds
Django Unchained

QUESTION 14 :

QUESTION 15 : SELECT film.titre FROM film, artiste WHERE film.idRéalisateur = artiste.idArtiste AND artiste.nom = 'Hitchcock' AND artiste.prénom = 'Alfred' AND film.idFilm NOT IN ( SELECT role.idFilm FROM role, artiste WHERE role.idActeur = artiste.idArtiste AND artiste.nom = 'Stewart' AND artiste.prénom = 'James' );
La Mort aux trousses
Rebecca
Les Enchaînés
Psychose

QUESTION 16 : 

QUESTION 17 : SELECT f.titre FROM film f LEFT JOIN role r ON f.idFilm = r.idFilm WHERE r.idFilm IS NULL;
La guerres des mondes

QUESTION 18 : SELECT f.titre FROM film f WHERE f.idFilm NOT IN ( SELECT n.idFilm FROM notation n JOIN internaute i ON n.email = i.email WHERE i.prénom = 'Prénom1' AND i.nom = 'Nom1' );

QUESTION 19 : SELECT DISTINCT a.nom, a.prénom FROM artiste a JOIN role r ON a.idArtiste = r.idActeur WHERE a.idArtiste NOT IN ( SELECT DISTINCT f.idRéalisateur FROM film f WHERE f.idRéalisateur IS NOT NULL );

QUESTION 20 : SELECT AVG(n.note) moyenne FROM notation n JOIN film f ON n.idFilm = f.idFilm WHERE f.titre = 'Memento';
Moyenne 8

QUESTION 21 : SELECT r.idArtiste, r.nom, r.prénom, COUNT(f.idFilm) AS nb_films FROM artiste r JOIN film f ON r.idArtiste = f.idRéalisateur GROUP BY r.idArtiste, r.nom, r.prénom;

QUESTION 22 : SELECT r.nom, r.prénom FROM artiste r JOIN film f ON r.idArtiste = f.idRéalisateur GROUP BY r.idArtiste, r.nom, r.prénom HAVING COUNT(f.idFilm) >= 2;

QUESTION 23 : SELECT titre
FROM notemoyenne
WHERE moyenne > 7;

