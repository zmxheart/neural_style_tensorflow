# neural-style

An implementation of [neural style][paper] in TensorFlow.

This implementation is a lot simpler than a lot of the other ones out there,
thanks to TensorFlow's really nice API and [automatic differentiation][ad].

TensorFlow doesn't support [L-BFGS][l-bfgs] (which is what the original authors
used), so we use [Adam][adam]. This may require require a little bit more
hyperparameter tuning to get nice results.

TensorFlow seems to be [slower][tensorflow-benchmarks] than a lot of the other
deep learning frameworks out there. I'm sure this implementation could be
improved, but it would probably take improvements in TensorFlow itself as well
to get it to operate at the same speed as other implementations. As of now, it
seems to be around 3x slower than implementations using Torch.

## Running

`python neural_style.py --content <content file> --styles <style file> --output <output file>`

(run `python neural_style.py --help` to see a list of all options)


## Requirements

* TensorFlow
* SciPy
* Pillow
* NumPy
* [Pre-trained VGG network][net] (MD5 `8ee3263992981a1d26e73b3ca028a123`)

## reference

\[neural-style \]: https://github.com/anishathalye/neural-style

\[net\]: http://www.vlfeat.org/matconvnet/models/beta16/imagenet-vgg-verydeep-19.mat

\[paper\]: http://arxiv.org/pdf/1508.06576v2.pdf

\[l-bfgs\]: https://en.wikipedia.org/wiki/Limited-memory_BFGS

\[adam\]: http://arxiv.org/abs/1412.6980

\[ad\]: https://en.wikipedia.org/wiki/Automatic_differentiation

\[tensorflow-benchmarks\]: https://github.com/soumith/convnet-benchmarks
