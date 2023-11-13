### Description

Figure out how they moved the flag.

### Approach

[pcapng](https://pcapng.com/) is a capture file format. 

To extract the files use Wireshark:

File > Export Objects > TFTP

which shows all the files recorded in the packet capture
![image](https://github.com/Harsha-creates/PicoCTF/assets/68886253/7218600d-2fc4-44dc-ac2c-c3069e6a8d80)

Click "Save All" to save them.

Analyze each one of them.

Open instructions.txt: `cat instructions`

```text
GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA
```

It's look like [ROT13](https://en.wikipedia.org/wiki/ROT13)

```code
echo "GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
`TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN`

If we add spaces we can see the hint

`TFTP DO ESNTENCRYPT OUR TRAFFIC SO WE MUST DISGUISE OUR FLAG TRANSFER.FIGURE OUT A WAY TO HIDE THE FLAG AND I WILL CHECK BACK FOR THE PLAN`

Open plan: `cat plan`
`VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF`

Once again, it is encrypted using ROT13. Here's the decrypted message

`IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS`

with some spaces:

`I USED THE PROGRAM AND HID IT WITH-DUEDILIGENCE.CHECK OUT THE PHOTOS`

## Pictures
