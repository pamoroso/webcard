![Icon of the NoteCards hypermedia system of Medley Interlisp.](https://raw.githubusercontent.com/pamoroso/webcard/main/notecards-icon.png)

# WebCard

WebCard is a NoteCards extension for visiting websites. It opens sites on the World-Wide Web using the browser of the host operating system on which Medley Interlisp runs.

The project is one of the entrants of the [RetroChallenge 2024](https://www.retrochallenge.org/2024/08/rc202410-registration-is-open.html). Follow the [project blog](https://journal.paoloamoroso.com/tag:WebCard) and the [status updates](https://fosstodon.org/@amoroso/tagged/RC2024).

WebCard is written in Interlisp as an extension of the [NoteCards](https://en.wikipedia.org/wiki/NoteCards) hypermedia system of [Medley Interlisp](https://interlisp.org).

![A website opened by WebCard, a NoteCards extension for visiting websites.](https://raw.githubusercontent.com/pamoroso/webcard/main/webcard.png)


## Requirements and dependencies

WebCard runs under Medley Interlisp and depends on the NoteCards hypertext environment of Medley Interlisp.

WebCard requires a host operating system that supports the `xdg-open` program of the [`xdg-utils`](https://www.freedesktop.org/wiki/Software/xdg-utils/) package, which should be installed before running WebCard. For example, Linux and other POSIX-like operating systems support `xdg-utils`.

What follows assumes familiarity with Medley Interlisp and NoteCards at the user level. If not the NoteCards and [Medley documentation](https://interlisp.org/software/using-medley) is recommended.

Only some chapters of the current version of the [NoteCards user manual](https://files.interlisp.org/medley/notecards/docs/user-guide-v1.2/) are available in PDF format, the rest is stored in corrupted TEdit files. However, a [prior edition of the NoteCards manual](https://files.interlisp.org/medley/notecards/docs/user-guide-v1.2/scanned/notecards_user_guide_v1.2.pdf) is available in full and, despite some user interface changes, nearly all of the material applies to the current system.


## Installation

To install WebCard download the source file [WEBCARD](https://github.com/pamoroso/webcard/blob/main/WEBCARD) from the project repo, copy it to a file system location your Medley Interlisp installation has access to, load NoteCards, change to that location, and compile the source by evaluating the following expression at an Interlisp Exec:

```
(TCOMPL 'WEBCARD)
```

Provide these answers to the questions the compiler asks:

* listing? no
* redefine? yes
* save exprs? no

Finally, load the compiled file by evaluating:

```lisp
(FILESLOAD WEBCARD)
```

If the file is not compiled evaluate instead:

```
(LOAD 'WEBCARD)
```

## Usage

Prior to using WebCard make sure NoteCards is loaded in Medley Interlisp. For example, from the host operating system pass the `-a` option to the `medley` script. Or click the `NOTECARDS` button on the Medley Interlisp desktop.

WebCard adds to NoteCards the new type of card "Web". Creating, accessing, and manipulating Web cards works the same way as for other card types except for what noted below. For example, you can execute the usual NoteCards commands to assign a title or designate a filebox as a container.


### Creating and managing Web cards

To create a new card of type Web in an open notefile, middle-click on the `New Cards` button of a notefile icon, then select `Web`. You'll be prompted to enter a URL which must be typed in full starting with `https://`, `http://`, or `mailto:`. If the input is invalid you'll be prompted again until you enter a correct URL.

The text area of the new card will display the associated URL. The text area is read only, so if you click and type there you'll get a warning. Select the `Close` option of the right-click title bar menu to dismiss the warning.

The left-click title bar menu provides two additional items specific to Web cards, `Visit URL` and `Edit URL`. The former unconditionally visits the URL associated with the card, the latter allows to change the URL.


### Traversing links to Web cards

To open the URL of a Web card traverse as usual a NoteCards link to the Web card, i.e. left-click on the link icon. This will both open the card if it isn't already, and open the URL in a new tab of the web browser. Link icons of Web cards have a bitmap that represents a card frame with at the center a globe crossed by meridians and parallels.

WebCard keeps track of visited URLs and tries not to open a new tab if it can determine a relevant one is already open.

Traversing the link to a closed Web card unconditionally visits the URL. Once the card is open, traversing the link again flashes the card to call attention to it but doesn't visit the URL. If a card flashes, check your web browser as the website is likely already open in a tab. The `Visit URL` command can force the visit though.

Closing a Web card discards the tracking information, so the next time link traversal reopens the card it will trigger an unconditional visit of the URL.


## Demo notefile

The file [`WCDEMO.NOTEFILE`](https://github.com/pamoroso/webcard/blob/main/WCDEMO.NOTEFILE) that comes with WebCard is a notefile with examples of Web cards filed into various types of cards such as Text cards and fileboxes. It contains some ready made Web cards to demonstrate what WebCard can do.

To explore the demo notefile open it from NoteCards as usual and traverse the links in the Table of Contents.


## Learn more

- [project blog](https://journal.paoloamoroso.com/tag:WebCard)
- [status updates](https://fosstodon.org/@amoroso/tagged/RC2024)
- [NoteCards](https://en.wikipedia.org/wiki/NoteCards)
- [Medley Interlisp](https://interlisp.org)


## Author

WebCard is developed by [Paolo Amoroso](https://github.com/pamoroso).


## License

This code is distributed under the MIT license, see the `LICENSE` file.
