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
    - Stylistic impact measured w.r.t. effect of style <br> _(i.e. how much the style has changed key elements of the output)_
 
To elaborate, to measure recognisability, we could measure the distance in melody and harmony between the input content and the output. To measure stylistic impact, we could measure the change in timbre, the effect on the spectograms, similarity to the style or even human feedback.

## Key concepts

- Broader concept (genus) is image generation (we aim to use image generation architecture due to availability and some interoperability)
- Style transfer is achieved inclusion of style loss between layers and content loss at the end
- Multiple styles can be combined using:
    - Composition of styles
    - Sequential training (first with one style then with the other)
    - Combined style loss

## References

- https://cs230.stanford.edu/projects_spring_2021/reports/76.pdf
- https://ashispati.github.io/style-transfer/
- https://arxiv.org/pdf/1803.06841v2.pdf
- https://link.springer.com/article/10.1007/s11760-023-02788-5
