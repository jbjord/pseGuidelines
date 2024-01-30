# Proposed Photosensitive Epilepsy Hazard guidance
This section is informative.

*This guidance extends other international guidelines to accommodate changes in technologies and content formats since those guidelines were initially developed. The basis for this text was originally from the paper "International Guidelines for Photosensitive Epilepsy: Review and Gap Analysis" by J. Bern Jordan and Gregg C. Vanderheiden (submitted January 2024). The [original guidance text from the paper](guidelinesFromPaper.md) is also available.*

## Proposed Provision (Normative)
There are no 1-second time spans, where there are more than 6 [luminance transition](#luminance-transition) or [red transition](#red-transition) [counts](#counts) where the transitions meet all the following criteria:

 1. Alternate in direction,
 2. Equal or exceed the [critical transition difference](#critical-transition-difference),
 3. Are of [qualifying duration](#qualifying-duration-working-value), and
 4. Have a summed area (including adjoining or nearby areas that are [sufficiently synchronized](#sufficiently-synchronized-working-value) to be treated as the same transition) that is equal to or greater than the [potentially hazardous area threshold](#potentially-hazardous-area-threshold).

## Proposed Definitions (Normative)
### Counts (transition counts)
Number of [luminance transitions](#luminance-transition) or [red transitions](#red-transition) that are not parts of [fast flashes](#fast-flashes).

_Note:_ Luminance transitions and red transitions are counted separately.

_Note:_ It is possible for a single transition to count as both a luminance and red transition.

_Note:_ Fast flashes are counted differently (see below).

### Luminance transition
Transition between higher and lower luminance states (in either direction).

### Red transition
Transition between a [saturated red](#saturated-red-equation) state and a different color state where the difference between states equals or exceeds the [critical transition difference](#critical-transition-difference) (in either direction, regardless of luminance).

_Note:_ The color states in a sequence of flashes do not need to match each other. 

### Fast flashes
Sequence of flashes where every second transition (i.e., every transition in the same direction) is separated by 15 ms or less.
 - When calculating transition counts, all transitions in the same direction in the fast flash sequence should be merged and counted as one transition (thus the sequence of fast flashes is counted as two transitions total). This merged flash should be analyzed (separately) as occurring at the start and again at the end of the sequence of fast flashes (but not both in the same analysis).

_Note:_ A flash rate of 65 Hz or faster (where leading edges of flashes are spaced 15 ms or less) is associated with significantly reduced risk.

### Critical transition difference
For a red transition, 
 - a color difference that is 0.2 units or greater on the 1976 CIE UCS chromaticity diagram between a [saturated red](#saturated-red-equation) state and a different color state.

For a luminance transition, 
 - a difference between a lower and higher level of luminance (going in either direction) of
   - if the lower luminance state is <80% of the **reference luminance** (see notes):
     - 10% of the reference luminance, or
   - else if the lower lunminance state is ≥80% of the **reference luminance**:
     - a [Michelson contrast](#michelson-contrast-equation) between states of 1/17. 

_Note:_ **Reference luminance** differs across technologies:
 - **For sRGB:** Both the peak and reference luminance for evaluation are a relative luminance of 1.0. The relative luminance (Y in the CIE XYZ color space, which ranges from 0 to 1) can be calculated with the transfer function specified in IEC 61966-2-1.  
 - **For standard dynamic range (SDR) television with standard color range (ITU-R BT.709) or wide color range (ITU-R BT.2020):** use the electro-optical transfer function in Annex 1 of ITU-R BT.1886 with both a reference luminance and screen luminance for white (_L<sub>W</sub>_) of 200 cd/m² and screen luminance for black (_L<sub>B</sub>_) of 0.0 cd/m².
 - **For Perceptual Quantization (PQ) high dynamic range (HDR) content:** use the reference luminance of 200 cd/m² and transfer functions specified in PQ tables in ITU-R BT.2100.
 - **For Hybrid Log-Gamma (HLG) HDR content:** use the reference luminance of 200 cd/m² and transfer functions specified in HLG tables in ITU-R BT.2100.
 - **For content to be displayed on known display hardware:** use the reference white luminance for the display, which is the peak luminance for SDR content. If the viewing environment is known, the reference luminance may be for vision adapted to that environment.

_Note:_ For typical indoor viewing environments, a reference luminance of 200 cd/m² is appropriate, which leads to a critical transition difference of 20 cd/m² when the darker state is <160 cd/m².

_Note:_ Theater viewing is often done with dark adapted viewing and a peak/reference luminance of 48 cd/m², which leads to a critical transition difference of 4.8 cd/m² when the darker state is <38.4 cd/m².

_Note:_ For HDR content, it is assumed that the content has been mastered so that 200 cd/m² is the reference white and that greater luminance is generally reserved for reflections, shine, and specular highlights of relatively small areas.

_Note:_ Luma, often denoted Y', is not the same as relative luminance, which is often denoted Y. Calculating relative luminance Y accurately from luma also requires two other components (for example, the C<sub>B</sub> and C<sub>R</sub> components of the Y'C<sub>B</sub>C<sub>R</sub> color space).

### Qualifying duration (working value)
The time over which a single transition may take place of 90 ms or less.

_Note:_ A slow change in luminance or color that takes more than 90 ms to reach or exceed the [critical transition difference](#critical-transition-difference) does not count as a flash transition.

_Note:_ This is a working value that may change as more is learned about photosensitive epilepsy. 

### Potentially hazardous area threshold
An area or collection of areas where the combined area equals or exceeds:
 - **For content on a known screen size and typical viewing distance:**
   - 0.006 steradians of any 10-degree field of view (equivalent to 25% of any 10-degree field of view) at the typical viewing distance.
 - **For content only shown on televisions of unknown screen sizes:**
   - 25% of the screen.
 - **For content displayed on screens of unknown type and size:**
   - 25% of any 416 × 416 px subarea of the content (where the "px" unit is a CSS pixel that is defined as 0.0213° viewing angle), analyzed when content is displayed at its largest size (without the user applying additional zoom).

_Note:_ A 23-inch (diagonal) Full HD monitor viewed at arm’s length can be used as a reference screen for scaling content displayed on screens of unknown types and sizes. This reference screen is 1920 × 1080 px (i.e., 0.0213° CSS pixels) and viewed at 71.1 cm (28 in.). 

_Note:_ See W3C CSS Values and Units Module Level 3 for definition of reference pixel (px).

_Note:_ The 25%-of-the-screen metric for television content was chosen for backwards compatibility. With modern displays and preferred viewing distances, the risk associated with 25% of the screen is increased compared to when the standards were first created.

### Sufficiently synchronized (working value)
When transitions are in the same direction and occur within 20 ms of each other.

_Note:_ Areas are added together for analysis when they transition in the same direction within 20 ms of each other.

_Note:_ This is a working value that may change as more is learned about photosensitive epilepsy and displays with high frame rates.

### Michelson contrast (equation)
```math
\frac{(L_{High}-L_{Low})}{(L_{High}+L_{Low} )} 
```
where $L_{High}$ and $L_{Low}$ are the luminance of the high and low luminance states, respectively.

### Saturated red (equation)
Colors where the red channel component is 80% or more of the total RGB color signal after gamma correction and any other transformations.
```math
R/(R+G+B) \geq 0.8 
```
where $R$, $G$, & $B$ are the normalized linear values of the red, green, and blue channels after gamma correction and any other transformations.

## References (Normative)
 - IEC 61966-2-1: Multimedia systems and equipment - Colour measurement and management - Part 2-1: Colour management - Default RGB colour space - sRGB. https://webstore.iec.ch/publication/6169
 - ITU-R BT.709: Parameter values for the HDTV standards for production and international programme exchange. https://www.itu.int/rec/R-REC-BT.709
 - ITU-R BT.1886: Reference electro-optical transfer function for flat panel displays used in HDTV studio production. https://www.itu.int/rec/R-REC-BT.1886
 - ITU-R BT.2020: Parameter values for ultra-high definition television systems for production and international programme exchange. https://www.itu.int/rec/R-REC-BT.2020
 - ITU-R BT.2100: Image parameter values for high dynamic range television for use in production and international programme exchange. https://www.itu.int/rec/R-REC-BT.2100
 - W3C CSS Values and Units Module Level 3. https://www.w3.org/TR/css-values-3/

## Acknowledgement (Informative)
Compiled by J. Bern Jordan and Gregg C. Vanderheiden under partial funding from grants #90REGE0008 and #90REGE0024 from the National Institute on Disability, Independent Living, and Rehabilitation Research (NIDILRR), Administration for Community Living (ACL), Department of Health and Human Services (HHS), and a gift from Meta (Meta Platforms, Inc.). The contents are those of the authors and do not necessarily represent the views of, nor an endorsement by the funders.

## License
<p xmlns:cc="http://creativecommons.org/ns#" >This work © 2024 by <span property="cc:attributionName">J. Bern Jordan and Gregg C. Vanderheiden</span> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg"></a></p>
