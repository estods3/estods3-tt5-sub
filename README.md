![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/wokwi_test/badge.svg)

# MNIST Neural Network Accelerator
This project is for a neural network accelerator ASIC for text recognition in MNIST handwritten digit dataset.
The chip is laid out into 4 main components:
<pre>


  
________          __________         __________         __________

|       |         |        |         |        |         |        |

|  I/O  |         | Memory |         |   NN   |         | Output | 

|       | ----->  |        | ----->  |        | ----->  |        | ---

|       |         |        |         |        |         |        |

|_______|         |________|         |________|         |________|
</pre>
## I/O
Read 28x1 images from I2C bus into memory. Read weights and biases for each neuron into memory.

## Memory
stores the 28x1 image as wel as the weights and biases for the neural network. memory will only be able to hold one image at a time.

## Neutal Network
Configure neural net with weights and biases and begin processing image from memory. return the classification of the image as a single byte as well as the confidence.

## Output
Display the decoded digit on 7 segment display. This section should incorporate logic to decode a binary coded decimal (BCD) into 7 segment logic for external 7 segment display.
Additionally, the output layer should trigger an additional digital pin as a flag to signal the image has finished being processed and another image can be fed in over I2C



### Tiny Tapeout
TinyTapeout is an educational project that aims to make it easier and cheaper than ever to get your digital designs manufactured on a real chip.

To learn more and get started, visit https://tinytapeout.com.

#### Wokwi Projects

Edit the [info.yaml](info.yaml) and change the wokwi_id to the ID of your Wokwi project. You can find the ID in the URL of your project, it's the big number after `wokwi.com/projects/`.

The GitHub action will automatically fetch the digital netlist from Wokwi and build the ASIC files.

#### Verilog Projects

Edit the [info.yaml](info.yaml) and uncomment the `source_files` and `top_module` properties, and change the value of `language` to "Verilog". Add your Verilog files to the `src` folder, and list them in the `source_files` property.

The GitHub action will automatically build the ASIC files using [OpenLane](https://www.zerotoasiccourse.com/terminology/openlane/).

#### Enable GitHub actions to build the results page

- [Enabling GitHub Pages](https://tinytapeout.com/faq/#my-github-action-is-failing-on-the-pages-part)

## Resources

- [FAQ](https://tinytapeout.com/faq/)
- [Digital design lessons](https://tinytapeout.com/digital_design/)
- [Learn how semiconductors work](https://tinytapeout.com/siliwiz/)
- [Join the community](https://discord.gg/rPK2nSjxy8)

- https://github.com/NNgen/nngen
- https://pypi.org/project/pyverilog/
- https://github.com/mchong6/MNIST-classifier-in-SystemVerilog
- https://github.com/pytorch/examples/blob/main/mnist/main.py

#### What next?

- Submit your design to the next shuttle [on the website](https://tinytapeout.com/#submit-your-design). The closing date is **November 4th**.
- Edit this [README](README.md) and explain your design, how it works, and how to test it.
- Share your GDS on your social network of choice, tagging it #tinytapeout and linking Matt's profile:
  - LinkedIn [#tinytapeout](https://www.linkedin.com/search/results/content/?keywords=%23tinytapeout) [matt-venn](https://www.linkedin.com/in/matt-venn/)
  - Mastodon [#tinytapeout](https://chaos.social/tags/tinytapeout) [@matthewvenn](https://chaos.social/@matthewvenn)
  - Twitter [#tinytapeout](https://twitter.com/hashtag/tinytapeout?src=hashtag_click) [@matthewvenn](https://twitter.com/matthewvenn)

