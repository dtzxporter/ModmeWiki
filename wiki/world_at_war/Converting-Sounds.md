# Converting Sound Files

## Required Tool
In this tutorial we use a tool called [Audacity](http://www.audacityteam.org/) which is provided free.

## Getting Started
Go ahead and open your source file, `audacity` can handle a lot of input files. Once open you'll notice the `track and a waveform` of the current file.

First off at the bottom left of your screen change the `sample rate to 44100`, this makes the project setting change to the rate we need. See below for an example.

{F3269}

Next go to the arrow at the top left of the current track and select `Rate->44100`.

{F3271}

> **NOTE:** If your sound file is already mono, you can continue to saving. Otherwise follow along below.

## Converting from Stereo to Mono
To convert from a `stereo to a mono track` you need to go to the arrow again at the top left of the current track and press `Split stereo to mono` This will create two separate tracks for you.

{F3273}

Now select both tracks using `shift` and go to `Track->Mix and render`, you will now see one combined track that will be `mono`.

{F3275}

## Saving the File
To save the file simply go to `File->Export Audio`, select `Wave and then signed 16 PCM`, This will provide a medium quality audio file.

{F3277}

You'll be presented with another dialog for file tags but be sure to ignore them and just continue, the file will have saved and it's ready for `Call of Duty: World at War` or conversion using the `Black Ops sound tool`.