## Poca
Poca is a fast, multithreaded and highly customizable command line podcast client, 
written in Python 3. 

### Features
Poca allows both for options for each individual subscription and
global defaults that apply to every subscription.

 * **Maximum amount.** Specify how many episodes the subscription should get 
   before deleting old episodes to make room for new ones.
 * **Override ID3/Vorbis metadata.** If you want _Savage Love_ to have _Dan 
   Savage_ in the artist field (rather than _The Stranger_), poca will 
   automatically update the metadata upon download of each new episode. Set
   'genre' to be overwritten by 'Podcast' as a default. Or have poca add track
   numbers to shows that have left them out.
 * **Filter a feed.** Only want news reports in the morning or on Wednesdays? 
   Use criteria such as filename and title, or the hour, weekday or date of 
   publishing to filter what you want from a feed.
 * **Rename files automatically.** Not all feeds have sensibly named media 
   files. Specify a renaming template like date_title to know what you're
   dealing with or to get alphabetical ordering to match chronology.
 * **From the top.** A latecomer to _Serial_ or other audiobook style podcasts?
   Poca introduces a special mode that gets the oldest episodes first, rather 
   than the latest. To move on to later episodes simply delete old ones and 
   poca will fill up with the next in line.
 * **Keeping track.** Poca logs downloads and removals to a local file so you
   easily see what's changed. Or configure it with an SMTP server and get
   notified when a feed stops working.
 * **Manage your shows.** by editing an easy-to-understand xml file. Or use
   the accompanying tool to add, delete, sort them, or get info about their
   publishing frequency, average episode length and more.

Poca also: has excellent unicode support for feeds, filenames and tags, gets 
cover images for feeds, has the ability to spoof user agents, can pause your
subscriptions, deals intelligently with interruptions, updates moved feeds
(HTTP 301) automatically, and more.

See the [Configuration](https://github.com/brokkr/poca/wiki/Configuration) 
section of the wiki for more details on features.

### Interface
[![asciicast](https://asciinema.org/a/pONMnNfk3TcqYolnz0y1kC3jG.png)](https://asciinema.org/a/pONMnNfk3TcqYolnz0y1kC3jG)

All configuration is done in a single XML-format file. For cron job 
compatibility, Poca has a quiet mode in addition to normal and verbose.

### Installing
You can install poca using only setuptools but `pip` is recommended. Find pip 
for your distro in your repositories (for debian/ubuntu its "python3-pip")

To generate a package installable by pip, in the source root directory (the 
one with setup.py) do:

    python3 ./setup.py sdist

And then install the generated package (using root privileges)

    pip3 install ./dist/poca-[VERSION].tar.gz

Running `poca` on a fresh install (no configuration) will place a copy of the 
example configuration in ~/.poca. The included feeds are there for illustrative
purposes. Edit the configuration file, try them out or use `poca-subscribe
delete` to clear it out and start afresh.

To remove Poca - having installed it using pip - simply do:

    pip3 uninstall poca

### Dependencies
 * You will need Python 3 for setup and running the program
 * The following third-party modules are required: `feedparser`, `lxml`, `mutagen`, `requests`
 * Pip can install all of these using 'pip3 install [name of module]'
