# Procedural Terrain Generation

<img src="demo.gif" width="1200" alt="Program Demo">

This script generates a procedural terrain based on layering [Perlin Noise](https://en.wikipedia.org/wiki/Perlin_noise#:~:text=Perlin%20noise%20is%20a%20type,1985%20called%20An%20image%20Synthesizer.). Perlin noise is a type of gradient noise which looks like this:

<img src="https://upload.wikimedia.org/wikipedia/commons/d/da/Perlin_noise.jpg" width="200" alt="Perlin Noise">

However, perlin noise by itself does not provide much detail. So to add more variation and detail to the noise, we add more layers of noise on top of one another. The **octave** is the number of layers we stack. The **lacunarity** is the amount we scale down each layer by which is calculated as follows:

<p align="center">
  <img height="25" src="https://render.githubusercontent.com/render/math?math=\text{frequency of layer}=\text{lacunarity}^n">
</p>

where ***n*** is the ***n***th layer we stack. The frequency of the layer is simply the scale of the noise. **Persistance** is how little we diminish the strength of each layer by. That is calculated as:

<p align="center">
  <img height="25" src="https://render.githubusercontent.com/render/math?math=\text{amplitude of layer}=\text{persistance}^n">
</p>

The amplitude is essentially the brightness of the noise. The **depth** increases the height of the terrain (amplifies the noise as a whole). The **width** and **height** controls how much area the base of the terrain covers. The **scale** scales the noise as a whole.
