

To start off this exploration I'm focusing on the features included in Godot's [Fast Noise Lite](https://docs.godotengine.org/en/stable/classes/class_fastnoiselite.html#class-fastnoiselite).

Any generated noisemap is defined by the Type of Noise used, the combination of a Fractal, and any additional Warping of it's domain.


# 1. Types of Noise

Variables
- Frequency: Lower frequency creates a more smooth noise while high frequency creates rougher, more granular noise.
- Offset: Translates the noise input coordinates.
- Seed: A random number that the noise map is constructed with.

## 1.1. Value
A lattice of values where each new value is determined by its neighboring values.

## 1.2. Value Cubic
Functions like value noise, but slower and with more variance at highs and lows. Avoids artifacts when generating a heightmap or bumpmap.

## 1.3. Perlin
A lattice of random gradients where dot products are used to determine the values between the lettuces (the cells).

## 1.4. Cellular
Can be Worley noise and Voronoi diagrams. Creates regions with a shared value.

Variables
- Cellular Jitter: Maximum distance a point can move off it's grid position (0 creates an even grid).
### 1.4.1. Cellular Distance Function
These are used to determine how the borders of each cell are determined which form a defined "group" of points.
- Euclidean: Finds the Euclidean distance to the nearest point to determine the shape of the cell, ensuring each cell contains only points that are closer to the center point than any other center point.
- Euclidean Squared: As above, but uses the Euclidean squared distance to the nearest point.
- Manhattan: Uses the Manhattan distance (taxicab metric) to the nearest point.
- Hybrid: Blends Euclidean and Manhattan to give curved cell boundaries.

### 1.4.2. Cellular Return Type
These are used to determine how the values of each point within a cell are determined.
- Cell Value: Returns the same value for all points within a cell.
- Distance: Returns a value determined by the distance to the nearest point (the center of the cell).
- Distance Two: Returns the distance to the second nearest point, the closest neighbor.
- Distance Two (Add, Sub, Multiply, Divide): Returns the nearest point (+ , - , * , / ) the second nearest point.
## 1.5. Simplex
Like Perlin, but gradients exist as a simplex lattice rather than a grid lattice to avoid directional artifacts.

## 1.6. Simplex Smooth
Higher quality but slower version of Simplex.

# 2. Fractals
Using fractals to modify any type of noise results in a noise map built on samples from multiple layers of noise maps.

Variables
- Gain: Determines the strength of each new layer of noise. Lower value places more emphasis on lower frequency base layers while a higher value puts more emphasis on higher frequency layers.
- Lacunarity: Multiplier between subsequent octaves. Higher value results in higher octaves which generates finer details and a rougher appearance.
- Octaves: The number of noise layers created and sampled to get the final value.

- Ping-Pong Strength: Determines the strength of the ping-pong fractal.
- Weighted Strength: Determines which octaves have the most impact on the final value, higher weighting gives more weight to higher octaves if lower octaves have a large impact.

## 2.1. Fractional Brownian Motion
Combines octaves into a fractal using fractional Brownian motion.

## 2.2. Ridged
Combines octaves in a way that results in a 'ridged' looking fractal.

## 2.3. Ping Pong
Combines octaves in a way that results in a ping-pong like fractal.

# 3. Domain Warp
This defines additional alterations to the generated noise map that are created by warping the domain of possible values.

Variables
- Amplitude: Sets the maximum warp distance the domain warp can shift a value from it's origin.
- Frequency: Determines the frequency of the noise that is used for warping the domain. Lower frequency is smoother while higher is rougher and more granular.

- Fractal Gain: When using a fractal, determines the strength of each subsequent layer of noise that is used to warp the space. Low value makes lower frequency layers stronger while high value makes higher frequency layers stronger.
- Fractal Lacunarity: When using a fractal, increasing this creates higher octaves which creates noise that has finer details and a rougher appearance.
- Fractal Octaves: When using a fractal, this determines the number of noise layers generated and sampled to get a final value for the fractal noise that warps the domain.
### 3.1.1. Domain Warp Type
- Simplex: Uses the simplex noise algorithm to warp the domain.
- Simplex Reduced: Uses a simpler simplex noise algorithm to warp the domain.
- Basic Grid: Uses a simple noise grid for the fastest but least complex warping of domain.
### 3.1.2. Domain Warp Fractal Type
- Progressive: Warps the space progressively by each octave to create a more 'liquified' distortion.
- Independent: Warps the space differently for each octave, resulting in a more chaotic distortion.