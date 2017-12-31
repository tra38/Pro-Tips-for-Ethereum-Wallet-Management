## Generating Safe Entropy (Randomness)

Entropy just means randomness or a source of randomness. The more random your sources of entropy are the stronger your key and password generation will be (ultimately helping to protect your funds more).

In his Bip39 tool, Ian Coleman describes good entropy generation and his tools use and source of entropy:

>Entropy values must be sourced from a strong source of randomness. This means flipping a fair coin, rolling a fair dice, noise measurements etc. Do NOT use phrases from books, lyrics from songs, your birthday or street address, keyboard mashing, or anything you think is random, because chances are overwhelming it isn't random enough for the needs of this tool.

>Do not store entropy.

>Storing entropy (such as keeping a deck of cards in a specific shuffled order) is unreliable compared to storing a mnemonic. Instead of storing entropy, store the mnemonic generated from the entropy. Steganography may be beneficial when storing the mnemonic.

>The random mnemonic generator on this page uses a cryptographically secure random number generator. The built in random generator can generally be trusted more than your own intuition about randomness. If cryptographic randomness isn't available in your browser, this page will show a warning and the generate button will not work. In that case you might choose to use your own source of entropy.

>You are not a good source of entropy.

Use a combination of any or all to generate your own source of entropy:
- Random keyboard smashing<sup>1</sup>
  - Remember to use SHIFT randomly for some uppercase and special characters.
  - Please don't break your keyboard.
- Using KeePassX built-in password generator (with all entropy settings enabled, and the length set to maximum).
- Rolling dice, flipping a coin and recording those numbers.
  - According to Christian Lundkvist, if you roll a set of 5 dice 10 times, you will get more than 128 bits of entropy, which should be sufficient for generating seeds/private keys.
- Mouse smashing with a virtual keyboard, like the Florence Virtual Keyboard in Tails OS.
   - To access the virtual keyword in Tails OS, click the keyboard icon on top of the screen.
- You can also try using the Unix system entropy generation `/dev/urandom` by running this script in a command line terminal (in Tails OS, you can access Terminal by Applications -> Favorites -> Terminal).

```
head -10 /dev/urandom | LC_ALL=C tr -dc 'a-zA-Z0-9~!@#$%^&*(){}[]"|?+="><__-' | head -n 1
```
	
Adjust the `-10` number for more or less lines of entropy.

**Comments**:
1 - "Random keyboard smashing"
While we recommend random keyboard smashing in the list of advice, the quote from Ian Coleman is opposed to "keyboard mashing". Is there a difference between the two? If not, should we still recommend it?

