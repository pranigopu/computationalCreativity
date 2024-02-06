# Computational creativity
## Conceptual map

### Overview
**CONSIDER AS YOU GO**: _Fundamental differences between human and computational creativity._

- Paradigms in AI
    - Problem solving
    - Artefact generation (main paradigm in computational creativity)
    - **CONSIDER**: _How thinking of AI as more than a problem-solving tool extends AI's potential?_
- Generative technology
    - Data-driven
    - Rule-based
 - Thinking generatively
    - Output vs. generation
    - Generative software <br> _Technically, all software is generative, but "generative software has a special meaning_
    - Artefact spaces <br> _A "space" is similar to the idea of a "sample space" of a random process_
        - Generative spaces
        - Possibility spaces
    - **CONSIDER**: _Generative vs. creative_
  
**NOTE: Generative system**: A generative system is a process which has unpredictable outputs affected by randomness shaped by procedures. A generative software is a kind of generative system; herein lies the difference between software as such (which is technically generative, in the sense of generating outputs) and "generative software".

**NOTE: Generative space and possibility space (and its purpose)**: <br> A generative space is the set of artefacts that a particular generative system is currently capable of generating. A possibility space is a set of artefacts meeting a particular definition; they define a broader class or "genus" to which the generative spaces of existing or potential generative spaces belong. The purpose of defining a possibility space is to help compare, plan and hypothesise about generative systems.

---

_Further topics_...

- `GAN`: Generative adversarial network
    - `GAN.prelim`: Preliminary concepts
        - Convolutional neural network (CNN)
        - Transposed convolutional neural network (TCNN)
    - `GAN.struct`: Structure of GAN
        - `GAN.struct.D`: Discriminator
        - `GAN.struct.G`: Generator
        - `GAN.struct`(`D`+`G`): Adversarial relationship & interaction
    - `GAN.InS`: Issues with GAN's & potential solutions <br> **KEY TOPIC DISCUSSED**: Wasserstein GAN (WGAN)
    - `GAN.WGAN`: Wassertein GAN <br> _... extends a solution_ `GAN.InS` (see full section below for more details)

**NOTE: Scope of computational creativity beyond DL methods**: <br> Computational creativity is much wider than deep learning (DL) methods such as GAN. Furthermore, such methods may be combined with DL for new, potentiall more effective results. For example, neurosymbolic methods may be used to provide an interesting template for DL methods to work from.

- `IG`: Image generation
    - `IG.appr`: Approaches to image generation
        - `IG.appr.1`: Produce valuable images as if handcrafted
        - `IG.appr.2`: Produce novel art from perceived imagination
        - `IG.appr.3`: Simulate creative practices of visual artists

### `GAN`: Generative adversarial network
- `GAN.prelim`: Preliminary concepts
    - Convolutional neural network (CNN)
    - Transposed convolutional neural network (TCNN)
- `GAN.struct`: Structure of GAN
    - `GAN.struct.D`: Discriminator
    - `GAN.struct.G`: Generator
    - `GAN.struct.(D+G)`: Adversarial relationship & interaction
- `GAN.InS`: Issues with GAN's & potential solutions
    - `GAN.InS.I`: Issues
        - (1): Difficult to train (w.r.t. data quantity & quality)
        - (2): Does not reliably converge to optimum
        - (3): Vanishing gradient
        - (4): Mode collapse
    - `GAN.InS.2`: Solutions
        - (3)+(4): Wasserstein GAN (WGAN)
- `GAN.WGAN`: Wasserstein GAN (WGAN) <br> _... extends_ `GAN.InS.S`.(3)+(4)
    - `GAN.WGAN.struct`: Structure of WGAN
        - CNN for discriminator
        - TCNN for generator

**NOTE: Reason for using CNN & TCNN for discriminator & generator**: <br> The discriminator needs to classify the image as real or fake and this process is best done using the feature extraction provided by CNN. The generator's aim is to fool the discriminator, hence its aim is to minimise the same objective function, hence, part of a generator's task is classification wherein it tries to match its output distribution as closely as possible to the reference distribution given in the training data. For this, the generator uses a CNN for this. However, CNN leads to downsampling, i.e. the output is much lower in resolution than the input. However, the generator must output fake images in the same shape as the training data for the discriminator to be able to input and classify. Hence, the output of the generator's CNN must be upsampled and a powerful method to do this is transposed convolution.

> READ MORE: https://analyticsindiamag.com/complete-guide-to-transposed-convolutions-in-cnn-models/

### `IG`: Image generation
- `IG.appr`: Approaches to image generation
    - `IG.appr.1`: Produce valuable images as if handcrafted
    - `IG.appr.2`: Produce novel art from perceived imagination
    - `IG.appr.3`: Simulate creative practices of visual artists
- `IG.choices`: Choices to make for image generation
    - Computer as a tool vs. computer as an autonomous creator
    - Human's role (artist, creator, technician or audience?)
    - Rule-based (symbolic) vs. example-based (sub-symbolic)
    - Purpose of image generation

_Working from_ `IG.appr.1`...

- `IG.GPM`: Graphics processing methods <br> _... extends_ `IG.appr.1`
    - `IG.GPM.pip`: Parts of the GPM pipeline
        - `IG.GPM.pip.IF`: Image filtering
        - `IG.GPM.pip.IC`: Image composition (combining images w.r.t. operations)
        - `IG.GPM.pip.FT`: Filter tree <br> _... extends_ `IG.GPM.pip.(IF+IC)`
        - `IG.GPM.pip.IS`: Image segmentation
        - `IG.GPM.pip.NPR`: Non-photorealistic rendering (ex. rendering as drawing, painting, etc.)

_Working from_ `IG.appr.2`...

- `IG.CFDG`: Context-free design grammar (symbolic method) <br> _Grammar implies a rule-based generative system_
    - Key elements for turning CFDG into a generative system
        - Probability of applying each rule at each step <br> **TIP**: _Consider a decision-tree for rule-application_
        - Associated transformation of each rule
- `IG.NST`: Neural style transfer (sub-symbolic method) 
    - `IG.NST.prelim`: Preliminary concepts
        - Pastiche in image generation
        - Content & style in image generation
    - `IG.NST.STwCNN`: Style transfer with CNN
        - `IG.NST.base`: Basic elements
            - (1): Content reference (i.e. content images for training)
            - (2): Style reference (i.e. style images for training)
            - (3): Balance between content & style <br> _How is this achieved? We shall discuss..._
        - `IG.CF`: Cost function for balanced multi-optimisation w.r.t. content & style <br> _... extends_ `IG.NST.base`.(3)
            - Style loss term
                - Gram matrix (preliminary concept)
                - Loss calculation with gram matrix
                - Choosing weight for style loss term
            - Content loss term
                - Loss calculation
                - Choosing weight for content loss term
            - Total loss term (weighted sum of the above)
