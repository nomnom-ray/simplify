## 3D Mesh Simplification

Implementation of
[Surface Simplification Using Quadric Error Metrics, SIGGRAPH 97](http://cseweb.ucsd.edu/~ravir/190/2016/garland97.pdf),
written in Go.

![Bunny](http://i.imgur.com/fcMpha3.png)

<p align="center">270,000 faces vs. 13,500 faces (5%)</p>

---

### Install

    go get -u github.com/fogleman/simplify/cmd/simplify

### Command-Line Usage

    Usage: simplify [-f FACTOR] input.stl output.stl

    $ simplify -f 0.1 bunny.stl out.stl
    Loading bunny.stl
    Input mesh contains 270021 faces
    Simplifying to 10% of original...
    Output mesh contains 27001 faces
    Writing out.stl

### API Usage

```go
// Use LoadSTL (ASCII) or LoadBinarySTL
mesh, err := simplify.LoadBinarySTL(inputPath)
// handle err
mesh = mesh.Simplify(factor)
mesh.SaveBinarySTL(outputPath)
```
