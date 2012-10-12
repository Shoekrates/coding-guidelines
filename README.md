CSS Coding Standards
====================

Inhalt
------

-   Kommentare
-   Struktur
-   Selektoren
-   Eigenschaften / Properties
    -   Anordnung
-   Werte / Values
-   Media Queries

Diese Coding Standards sollen als Grundlage für die Zusammenarbeit bei
der Erstellung von Stylesheets dienen. Der Text basiert in großen Teilen auf den Wordpress Coding Standards: 
[http://make.wordpress.org/core/handbook/coding-standards/css/](http://make.wordpress.org/core/handbook/coding-standards/css/)


Kommentare
---------------------------

Mehrzeilige Kommentare sind zu platzieren:

-   am Beginn jeder Datei
    -   mit Angabe wozu und an welcher Stelle das Stylesheet benötigt
        wird, kurze Inhaltsangabe o.ä.
    -   Abhängigkeiten

-   vor jedem Themenabschnitt

Durch eine korrekte Benennung der Abschnitte lässt sich die CSS-Datei
sehr einfach durchsuchbar machen, z. B. “Navigation”.

    /**
     * Stylesheet für Website domain.de
     * Autor: Autor
     * Stand: xx.xx.2012
     */

In allen anderen Fällen ist der Zeilenkommentar zu nutzen:

    /* Dies ist ein einzeiliger Kommentar */

Struktur
-----------------------

Es gibt viele Wege ein Stylesheet zu strukturieren. Ziel ist immer eine
gute Lesbarkeit des Codes.  
Ein paar Grundregeln:

-   Verwende Tabs statt Leerzeichen, um Eigenschaften einzurücken. Ein
    Tab entspricht der Breite von vier Leerzeichen, (dies kann je nach
    eingesetztem Editor in den Einstellungen definiert werden).
-   Bei mehreren Selektoren, sollte jeder Selektor eine eigene Zeile
    bekommen, die mit einem Komma endet.
-   Nach dem letzten Selektor folgt ein Leerzeichen und die öffnende
    geschweifte Klammer
-   Eigenschaften-Wert Paare bekommen eine eigene Zeile, sind mit einem
    Tab eingerückt und enden mit einem Semikolon. Das gilt auch für die
    letzte Eigenschaft im Selektor!
-   Die schließende geschweifte Klammer kommt in eine eigene Zeile und
    wird ausgerückt. Danach folgt eine Leerzeile.

Richtige Anwendung:

    .selector-1,
    .selector-2,
    .selector-3 {
         display: block;
         color: #000;
    }

Falsche Anwendung:

    .selector-1, .selector-2, .selector-3 {
         display: block;
         color: #000;
         }

    #selector-1 { display: block; color: #000; }


Selektoren
---------------------------

Aufgrund der Spezifität sollte mit Selektoren verantwortlich umgegangen
werden. Hinterfrage jeden Selektor, ob er in dieser Art und Weise
sinnvoll gesetzt ist.

-   Benutze ausschließlich Kleinbuchstaben für Selektoren. Bei
    zusammengesetzten Worten, benutze bitte Bindestriche. höchstens 1
    Zusammensetzung. Vermeide CamelCase oder Unterstriche.
-   Benutze Menschen-lesbare Selektoren, die beschreiben, welches
    Element Sie gestalten.
-   Attribut-Selektoren sollten Anführungstriche um den Wert nutzen.
-   Benutze keine überqualifizierten Selektoren, `div.container`
    funktioniert auch einfach so: `.container`

Richtige Anwendung:

    .modul-box {
         margin: 1em 0;
    }

    input[type="text"] {
         line-height: 1.1;
    }

Falsche Anwendung:

    .modulBox { /* Vermeide CamelCase. */
         margin: 0;
    }

    .modul_box { /* Vermeide Unterstriche. */
         margin: 0;
    }

    div.modul-box { /* Vermeide Überqualifikation. */
         margin: 0;
    }

    .f3-pt { /* Was bedeutet f3-pt?! Benutze einen sinnvollen Namen. */
         margin: 0;
    }

    input[type=text] { /* Denk' an die Anführungsstriche: [type="text"] */
         margin: 0;
    }


Eigenschaften / Properties
---------------------------------

- Eigenschaften werden immer klein geschrieben, Ausnahmen: Schriftname, Vendor-Prefix
- Nach der Eigenschaft folgt der Doppelpunkt, danach eine Leerstelle
- Jede Eigenschaft bekommt eine eigene Zeile
- Vermeide Wiederholungen von Eigenschaften, die bereits durch Vererbung festgelegt wurden
- Nutze für Farbdeklarationen Hex-Code oder rgba(). Bitte keine RGB-Werte oder Großschreibung, falls gekürzt werden kann, kürzen: `#FFFFFF` = `#fff`
- Wenn möglich, Kurzschreibweise benutzen, z. B. bei background, border, font, list-style, margin und padding.

### Anordnung
- Grundlage für die Anordnung sollte sein:
  - Display
	- Position
	- Box Model
	- Farbe und Typo
	- Anderes

Werte / Values
----------------------

- Nach dem Doppelpunkt kommt eine Leerstelle
- Immer mit einem Semikolon abschließen
- Immer doppelte Anführungsstriche statt einfachen benutzen
- der Wert "0" hat keine Einheit
- Für Dezimalwerte bitte eine führende 0 benutzen: `0.5em` statt `.5em`

Richtige Anwendung:

	.klasse { /* Korrekte Schreibweise für Anführungsstriche */
    	background-image: url("images/bg.png");
    	font-family: "Helvetica Neue", sans-serif;
	}
	.klasse { /* Korrekte Schreibweise für "0"-Werte */
    	font-family: Georgia, serif;
    	text-shadow: 0 -1px 0 rgba(0, 0, 0, 0.5),
                  0 1px 0 #fff;
	}

Falsche Anwendung:

	.klasse { /* Vermeide fehlende Leerstelle sowie fehlendes Semikolon */
        background:#fff
	}
 
	.klasse { /* Vermeide Einheiten bei "0"-Werten */
        padding: 0px 0px 20px 0px;
	}


Media Queries
---------------------

- Media Queries sollten möglichst direkt unter der ursprünglichen Deklaration eines Selektors folgen, um die Wiederfindbarkeit zu wahren