
# Fortune repository 

Contains quotes of interest mostly from from books I read.

## How to install the fortune app

```bash
$ sudo apt install fortune fortunes-bofh-excuses fortunes-ubuntu-server
# add fortune to .bashrc so it runs every time a terminal is opened
$ echo fortune >> ~/.bashrc
```

## How to create fortune data

For this example we will store all our quotes in a file named ```quotes```. 
It's contents will be delimited by % sign like below:

```
Limits exist only in your mind!
%
"Maybe this world is another planet’s hell."
— Aldous Huxley
%
"Choices are the hinges of destiny." —Edwin Markham
```

------------

To allow the fortune app to extract random entries from  our quotes file we need to generate a .dat file. We do this by running the command below:

```bash
# generate the .dat file
$ strfile -c % quotes quotes.dat
```

------------
To test our newly generated fortune data run:

```bash
# test the fortune file we created
$ fortune quotes
```

------------
To add our quote file to the default fortune app repository run:

```bash
# copy both the text file and the .dat file to fortune folder
$ sudo cp quotes* /usr/share/games/fortunes
$ cd /usr/share/games/fortunes
$ sudo chmod 644 quotes*
$ sudo ln -s quotes quotes.u8
```

------------