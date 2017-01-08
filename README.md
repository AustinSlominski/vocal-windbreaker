# Vocal Windbreaker
Generative soundscape using sonified video and ambient room (and vocal) sounds

The goal is to explore smooth, ambient, generative soundscapes, using various sound sources. It will combine three different components:

* Video Sonification
* Ambient Sounds
* Vocal Sounds

The video sonification will take in video, at least right now, from a web cam. This will hopefully be a macro-scale effect, shaping dynamics or shaping textural effects upon the real sound sources.

The ambient sounds will be some sort of amalgamation of room sounds, sampled over time. I would really like to see sampling taking place over long periods of time, similar to this piece, [Space Replay](http://ied.rca.ac.uk/de-computation/space-replay). 

Vocal sounds should have some sort of prominence, with some sort of basic recognition of vocal and non-vocal sounds. I would expect the ambient sounds to be largely non-literal, or not entirely recognizable, while vocals are treated more deliberately and replayed more recognizably. 

## Steps for ambient sound layer

First, I need to start considering some of the ambient sound sampling methods. This is the real structural element, so it seems like the right spot to start. I'll begin by pulling in my laptop microphone input, and then will try a couple different methods:

1. Grain capture at varying lengths (mid to long) and at varying intervals, then wave~ playback.
2. Delayed input, mixing with both current and past input, overlapping at different, dynamic rates. (groove~ and wave~)

The first method, I have a feeling, will be a little more hard-edged. At short grain lengths, it will be rough and buzzsaw-like, and at long grain lengths, it will sound something like a digital delay freeze. 

The second method would likely be smoother. If I mix the current input with repitched or retimed delayed input, you would get some interesting juxtapositions between the current moment and the moment before. And there would also be the possibility for some sort of visual representation of this as well down the line.

## Steps for vocal sound layer

If I choose to use the second method for the ambient sound layer, I might be able to use the first method to create the vocal layer. Mid-length to long samples, pulled from voices in the space, would sound more prominent being hard-edged. With this, I could modulate different aspects of the voice, whether it's pitch, rate, or grain length. 

### Detection of vocal sounds

I know there are methods for this, but I will have to do some exploring.

https://cycling74.com/forums/topic/need-voice-detection-not-speech-recognition/#.WHGTv7YrK34

This link suggests, at least initially, filtering out all non-vocal frequencies, below 200hz and above 2000hz. 

My other thought would be detecting significant channges in spectra, maybe using FFT to detect deviations in average sounds, triggering a gate to open, record samples, and then close once it is returned to the 'room average'.
