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

## 5. Rendering Generic 3D Representations

### 5.1 Rendering Point Clouds

> *From left to right: Point cloud for image 1, image 2, combined*

<div style="display: flex; gap: 10px">
<img src="outputs/spinning_cloudpoint_1.gif" height=300>
<img src="outputs/spinning_cloudpoint_2.gif" height=300>
<img src="outputs/spinning_cloudpoint_combined.gif" height=300>
</div>

### 5.2 Parametric Functions

1. Torus

<img src='outputs/spinning_torus_pointcloud.gif' height=300>

2. Hyperboloid

<img src='outputs/spinning_hyperboloid_pointcloud.gif' height=300>

### 5.3 Implicit Surface

<br>


1\. Torus

<img src='outputs/torus_implicit copy.gif' height=300>

<br>

2\. Hyperboloid

<img src='outputs/hyperboloid_implicit.gif' height=300>

<br>

3\. Trade-offs between rendering a mesh vs a point cloud

> Discuss some of the tradeoffs between rendering as a mesh vs a point cloud. Things to consider might include rendering speed, rendering quality, ease of use, memory usage, etc.

- Point clouds:
    + Higher rendering quality (by being able to capture fine details and textures)
    + Higher memory usage (especially for rendering dense regions of point cloud)
    + Lower ease-of-use (point cloud must be pre-processed before it can be used in 3D applications)
    + Lower rendering speed

- Meshes:
    + Lower rendering quality
    + Lower memory usage
    + Higher ease-of-use
    + Higher rendering speed

## 6. Do Something Fun


## 7. Sampling Points on Meshes

> Sampling to cloud point: 10, 100, 1000, 10000 and 100000 points.

<img src='cow_og.gif' height=300>
<img src='outputs/cow_10.gif' height=300>
<img src='outputs/cow_100.gif' height=300>
<img src='outputs/cow_1000.gif' height=300>
<img src='outputs/cow_10000.gif' height=300>
<img src='outputs/cow_100000.gif' height=300>
