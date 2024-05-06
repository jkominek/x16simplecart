# Simple Cartridge Tutorial for the Commander X16

So you'd like to make your own cartridge. You'll need a circuit,
and a circuit board. (And then stuff to put on it.)

What we've got here is a PDF with a schematic. You can replicate it
yourself in KiCad, tweaking it to suit your needs, and then use the
use footprints in my [KiCad
library](https://github.com/jkominek/x16expansion) to lay out the PCB
quickly and easily. By going that route, you can use surface mount parts
if you want, or remove the I2C EEPROM (or add another one!), or enlarge
the board to have even more storage.

Or you can go over to the [releases
section](https://github.com/jkominek/x16simplecart/releases) and grab
some Gerber files that you can upload to JLCPCB. You can't change those,
though. They're licensed CC BY-NC-ND 4.0, so you can have them made
for yourself, and only yourself. No group buys, no taking my name out
of the silkscreen and selling them on eBay, etc, etc. If you'd like
to use my design for a commercial purpose, I'd be happy to license
it to you for a small fee. If you'd like a different PCB designed, I'm
available for that work, as well.

## BOM

Here's the bill of materials for the layout in the Gerber files:

* SST39SF040-70-4C-PHE
  * The FLASH memory, same as the CX16 motherboard uses.
* 24LC128-I/P
  * I2C EEPROM
* SN74ACT00N
  * NAND gates
* CD74ACT138E
  * Address decoder
* RCER71H105K2DBH03A
  * Decoupling capacitors

All of those are currently available from Digikey, and I'd expect them
to be available from most other major suppliers. The 74xx series parts
and capacitors are easily swapped out. There are probably plenty of
alternative I2C EEPROMs as well. But there isn't a lot of asynchronous
FLASH memory made anymore, so plan on sticking with that part.

You could add on some DIP sockets if you don't want to solder
your chips straight to the board. But they probably won't fit in a
case if you add sockets. Speaking of which they were tested with this
case:

* https://www.muramasaentertainment.com/product/famicom-cartridge-shell-transparent/
