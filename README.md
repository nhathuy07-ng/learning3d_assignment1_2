# Submission file for learning3d/assignment1

## 0. Rendering First Mesh

<img src="outputs/cow.png" height=300></img>

## 1. Practicing with Cameras

### Spinning cow with solid color
<img src="outputs/cow.gif" height=300>

### Dolly Zoom effect
<img src="outputs/cow_dolly.gif" height=300>

## 2. Practicing with Meshes

### Tetrahedron
<img src="outputs/gif_tetrahedron.gif" height=300>

### Cube
<img src="outputs/gif_cube.gif" height=300>

## 3. Re-texturing a Mesh
<img src="outputs/gif_cow_retextured.gif" height=300>

## 4. Camera Transformation

- `T_relative` transform the position of the world origin relative to camera space.
    + `T_relative` takes the form of `[x, y, z]`
    + `x` moves the origin to the left if positive, right if negative.
    + `y` moves the origin up if positive, down if negative.
    + `z` moves the origin further into the screen if positive, in opposite direction if negative.

- `R_relative` rotates the camera around the origin (extrinsic rotation). Given `R_roll`, `R_pitch`, `R_yaw` being the individual (relative) rotational matrices, `R_relative` = `R_roll @ R_pitch @ R_yaw`

### Original rotation and transformation

<img src="outputs/cow_transform_0.png" height=300>

### Transformations

1\.
```
R_relative = [
    [cos(-pi / 2), -sin(-pi / 2), 0],
    [sin(-pi / 2), cos(-pi / 2), 0],
    [0, 0, 1]
]

T_relative = [0, 0, 0]
```

<img src="outputs/cow_transform_1.png" height=300>

2\.
```
R_relative = [
    [1, 0, 0],
    [0, 1, 0],
    [0, 0, 1]
]

T_relative = [0, 0, 2]
```

<img src="outputs/cow_transform_2.png" height=300>

3\.
```
R_relative = [
    [1, 0, 0],
    [0, 1, 0],
    [0, 0, 1]
]

T_relative = [0.5, -0.5, 2]
```

<img src="outputs/cow_transform_3.png" height=300>

4\.
```
R_relative = 
[
    [cos(pi/2), 0, sin(pi/2)],
    [0, 1, 0],
    [-sin(pi/2), 0, cos(pi/2)]
]

T_relative = [0, 0, 0]
```

<img src="outputs/cow_transform_4.png" height=300>

## 5. Rendering Point Clouds