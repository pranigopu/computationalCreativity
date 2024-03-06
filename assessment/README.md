# Neural Style Transfer in Audio & Music

- **Project type**: Weak computational creativity (focus is on generating valuable artefacts)
- **Focus**: Style transfer between audio data (music as content, audio or music as style)

With respect to the style transfer...

- **Content**: Melodies, pieces, songs
    - Preferably with clear voices and tones (to enable easier evaluation of retained musicality)
    - Content must remain relatively recognisable w.r.t. melody and harmony
- **Style**: Ambience, ambient music, sound textures

Aims...

- Enable change in timbre, quality and sound effects (ex. reverb, echo, distortion) w.r.t. style
- Combine two or more styles
- Evaluate the quality of output w.r.t. (1) recognisability and (2) novelty
    - Recognisability measured w.r.t. content
    - Novelty measured w.r.t. effect of style (i.e. how much the style has changed key elements of the output)
 
To elaborate, to measure recognisability, we could measure the distance in melody and harmony between the input content and the output. To measure novelty, we could measure the change in timbre, the effect on the spectograms, similarity to the style or even human feedback.
