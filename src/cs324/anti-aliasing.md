# Anti-Aliasing

- Used to tackle two major problems of aliasing
  - Jaggies
  - Texture Aliasing - High frequency components too finely spaced for point sampling

## Nyquist Sampling

- Signal can be reconstructed if sampled at rate more than twice as high as highest frequency in signal
- Problem - math objects exist with higher frequencies than what we can display

## Anti-Aliasing solutions

- Increase sampling rate of display
  - Not practical for display techs
  - Upper end of printing tech
  - Increased frame buffer sizer
  - Increased object rendering time
- Super Sampling & Post Filtering
  - Computationally complex (not worth for finite width objects)
- Area sampling (pre-filtering)
  - Compute area of overlap before point sampling
  - Two main approaches
    - Unweighted - In practise, primitives can never be thinner than one pixel across
      - Intensity decreases the further from pixel centre
      - Line not crossing pixel -> No influence
      - Equal areas -> equal intensity
    - Weighted - Gives more weight to areas closer to pixel centre
      - Intensity decreases the further from pixel centre
      - Line not crossing pixel -> No influence
      - Equal areas -> unequal intensity, area closer to pixel -> more contribution
