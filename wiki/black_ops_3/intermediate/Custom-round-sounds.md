#Setting up sounds==
To set up your sounds so they work with Black Ops III, you need to use a program such as Audacity. Make sure your project rate in hertz is set to 48000 and that when you export the format is WAV (Microsoft) signed 16-bit PCM like in these screenshots:
{F2479}

{F2481}

That's the first part done. Your sounds will now work in Black Ops III, but you now need them in-game.

#Exporting sounds==
Make sure you export your sounds to sound_assets in your Black Ops III folder, just make a folder inside there and put your sounds into it.
 
#Setting up the aliases==
From the root Black Ops III folder, go to share/raw/sound/aliases/. In here you should find user_aliases.csv. Open the file and add these lines somewhere inside it:


1. Round Sounds
mus_roundstart_first_intro,,,your_folder\intro.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundstart_short1_intro,,,your_folder\short1.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundstart_short2_intro,,,your_folder\short2.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundstart_short3_intro,,,your_folder\short3.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundstart_short4_intro,,,your_folder\short4.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundstart1_intro,,,your_folder\start1.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundstart2_intro,,,your_folder\start2.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundstart3_intro,,,your_folder\start3.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundstart4_intro,,,your_folder\start4.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_roundend1_intro,,,your_folder\end.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_dogstart1_intro,,,your_folder\dogstart.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_dogend1_intro,,,your_folder\dogend.wav,,,UIN_MOD,,,,,,,,,,,95,95,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_gameover_intro,,,your_folder\gameover.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,


NOTE: There are 8 possible round sounds you can have. This is because The Giant has 8 round sounds in total. You can absolutely set all of them to the same sound and it will play just one round sound. However, if you do want multiple sounds, note that the mus_roundstart_shortX_intro round sounds play from round 6 and are intended to be shorter sounds. The others, mus_roundstartX_intro play from round 2 to 5. This means that you can only really have four custom round sounds if you want the same ones to be playing throughout the whole game.

|mus_roundstart_first_intro|the round sound that plays when you first spawn in|
|mus_roundstart_short1_intro|the first randomly picked round sound that plays from round 6|
|mus_roundstart_short2_intro|the second randomly picked round sound that plays from round 6|
|mus_roundstart_short3_intro|the third randomly picked round sound that plays from round 6|
|mus_roundstart_short4_intro|the fourth randomly picked round sound that plays from round 6|
|mus_roundstart1_intro|the first randomly picked round sound that plays from round 2 to 5|
|mus_roundstart2_intro|the second randomly picked round sound that plays from round 2 to 5|
|mus_roundstart3_intro|the third randomly picked round sound that plays from round 2 to 5|
|mus_roundstart4_intro|the fourth randomly picked round sound that plays from round 2 to 5|
|mus_roundend1_intro|the round end sound|
|mus_dogstart1_intro|the dog round start sound|
|mus_dogend1_intro|the dog round end sound|
|mus_gameover_intro|the game over music|

To add your sound in, replace your_folder with the folder you made earlier in sound_assets and replace the wav file name that comes after the folder with whatever you've named your specific sound. For example, in my case my folder is round_sounds and if I was for example wanting to add in my custom round start sound named aldwychrs.wav to replace mus_roundstart1_intro, the line for mus_roundstart1_intro would end up looking like this:


mus_roundstart1_intro,,,round_sounds\aldwychrs.wav,,,UIN_MOD,,,,,,,,,,,100,100,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,


And you're done! Save the file and compile and link your mod and your custom round sounds will now be in-game.

//**Contributors**//
The Black Death