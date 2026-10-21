portrait.jpg                   - hero photo on the home page (900x900)
favicon.png                    - 96x96 browser tab icon, the brain drawing. 96 because Google
                                 only shows a site icon in search results if it is a
                                 multiple of 48px square.
figure-earthworm-sem.jpg       - SEM of an Eisenia hortensis head, research.html earlier-work
                                 section. Credited in the figcaption. 1200x1200 greyscale,
                                 from a 2048x2048 original on Wikimedia Commons.
figure-mixtures-abstract.jpg   - graphical abstract of the Cell Reports paper, research.html
                                 odor-mixtures section. 996x996, copied verbatim from
                                 inputs/ga1_lrg.jpg with no re-encode.
figure-octopus-arm.gif         - one 320x160 GIF holding both panels: backlit video of an
                                 octopus arm reaching for food (left) and its segmentation mask
                                 (right). Each panel is a 160px square crop around the arm's
                                 full range of travel, from inputs/giphy.gif (480x360, 6.7 MB)
                                 and inputs/200.gif. Both sampled on a shared 120ms grid,
                                 44 frames -> 422 KB. Composited into a single file because two
                                 separate GIFs cannot stay in sync across loops.

                                 Two encoder settings matter here. Quantise against a FIXED
                                 48-level grey ramp, not an adaptive palette: an adaptive
                                 palette spends its entries on the mask's pure black and white
                                 and the arena's narrow bright range, giving errors up to 25
                                 grey levels and a washed-out, blown-looking video panel. The
                                 grey ramp holds it to 6. And write disposal=1, not 2:
                                 disposal=2 clears untouched regions to the background colour
                                 each frame, which bled white across the black mask panel.
                                 Do not "fix" the brightness with a tone curve -- the source
                                 grading is correct and clips at the top on purpose.
McCalmon_CV.pdf                - downloadable CV linked from cv.html. Generated from cv.html
                                 itself using the @media print rules in styles.css, via
                                 headless Chrome:
                                   chrome --headless --no-pdf-header-footer \
                                     --print-to-pdf=assets/McCalmon_CV.pdf cv.html
                                 Rerun after editing cv.html.

Both octopus GIFs would be roughly a quarter the size as MP4/WebM if ffmpeg becomes
available. The earlier micro-CT rotation still and GIF were removed when these replaced
them; the source is still inputs/octo gif.gif.
