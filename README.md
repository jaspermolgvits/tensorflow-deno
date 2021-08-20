# TensorFlow for Deno


WIP


Very basic implementation of the Node.js backend for Tensorflow.js in Deno.





```javascript
import tf from "https://deno.land/x/tensorflow/tf.js";

const model = tf.sequential();
model.add(tf.layers.dense({units: 1, inputShape: [1]}));

// Prepare the model for training: Specify the loss and the optimizer.
model.compile({loss: 'meanSquaredError', optimizer: 'sgd'});

// Generate some synthetic data for training.
const xs = tf.tensor2d([1, 2, 3, 4], [4, 1]);
const ys = tf.tensor2d([1, 3, 5, 7], [4, 1]);

// Train the model using the data.
model.fit(xs, ys).then(() => {
// Use the model to do inference on a data point the model hasn't seen before:
// Open the browser devtools to see the output
model.predict(tf.tensor2d([5], [1, 1])).print();
});
```



**TODO:**

Find and fix bugs (ther' be many...).

Add and use WebGPU backend as the default backend.
