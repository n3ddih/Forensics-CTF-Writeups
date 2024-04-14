# FU Secathon Writeup

2021 - Forensics category - FRS302

## Briefing

The challenge is an audio that have morse code in it, but it also contains background noises that is hard seperate from the morse sound.

By viewing the spectrogram of the audio in Audacity, it is possible to write the morse code dow; then decode it in [dcode.fr](https://www.dcode.fr/morse-code)

[Download file here](echoslambyjava.wav)

## Details

Open the wav file and view the spectrogram of it.

![image](https://user-images.githubusercontent.com/80664686/138596966-0b0132ac-987d-4d73-9633-b4166f79e4a9.png)

As you can see, there are lines that represent the morse audio.

We can manually view and write down the morse code using this rule.

> Short line for a *(.)*</br>
> Long line for a *(-)*</br>
> Short gap for a *space*</br>
> Long gap for a *(/)*

**Bonus**: In Audacity, the *spectrogram settings* like below can help with easier inspection.

![image](https://user-images.githubusercontent.com/80664686/138599249-6135611c-1c8e-45a2-900e-8c7cfa1605c1.png)

> Morsecode:</br>
> .-.. .- -.- .- -../-- .- - .- - .- --./-. --- .-. -- .- .-.. .. -./-. --- .-. -- .- .-.. .. -./. -.-. .... ---/... .-.. .- --/-... -.--/.--- .- ...- .-/--- -.--/--- -.--/--- -.--/--- -.--/--- -.--/--- -.--/--- -.--/--- -.--/--- -.--

The morse code can be decoded using [dcode.fr](https://www.dcode.fr/morse-code)

![image](https://user-images.githubusercontent.com/80664686/138600380-1a9b218e-1f45-49ec-a61d-7a1102964574.png)

> Flag: FUSEC{LAKADMATATAGNORMALINNORMALINECHOSLAMBYJAVAOYOYOYOYOYOYOYOYOY}
