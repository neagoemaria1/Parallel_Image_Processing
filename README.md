# Parallel Image Processing with OpenCV, MPI and CUDA

A C++ image processing project that implements and compares three different approaches for resizing images and converting them to grayscale:

- Sequential CPU processing
- Parallel CPU processing with MPI
- GPU processing with CUDA

The project uses OpenCV for image loading and saving, while the image processing operations are implemented directly at pixel level.

## Features

- Image loading and saving using OpenCV
- Custom image resizing
- Grayscale conversion
- Sequential CPU implementation
- MPI-based parallel implementation
- CUDA-based GPU implementation
- Execution time measurement
- Support for large images
- Output image generation

## Implementations

### Sequential Version

The sequential version processes the entire image using a single CPU process.

It performs:

- image loading
- image resizing
- grayscale conversion
- execution time measurement
- output image generation

### MPI Version

The MPI version distributes the image processing workload across multiple CPU processes.

The image is divided into sections, and each process handles a portion of the image. The processed sections are then combined to generate the final result.

The MPI implementation uses process communication and synchronization to distribute and collect image data.

### CUDA Version

The CUDA version performs the image processing operations on the GPU.

Image resizing and grayscale conversion are executed in parallel, allowing multiple pixels to be processed simultaneously.

## Image Processing Operations

### Image Resizing

The image is resized using a custom pixel-by-pixel implementation based on the original and target image dimensions.

### Grayscale Conversion

The resized image is converted to grayscale using the weighted intensity formula:

```text
Intensity = 0.299 * Red + 0.587 * Green + 0.114 * Blue
```

## Performance Measurement

The execution time of the image processing operations is measured using the C++ `<chrono>` library.

The program measures:

- image resizing time
- grayscale conversion time

This allows the three implementations to be compared in terms of execution approach and performance.

## Input and Output

The program loads an input image and asks the user to define the desired output dimensions.

Example:

```text
Please define the new size of the image
Width: 1280
Height: 720
```

The application generates:

- a resized image
- a grayscale version of the resized image

The MPI version can also generate intermediate image sections processed by individual processes.

## Technologies

- C++
- OpenCV
- MPI
- CUDA
- Parallel Programming
- GPU Computing
- Image Processing

## Project Purpose

The purpose of this project is to study and compare different approaches to image processing using sequential execution, CPU-based parallel processing, and GPU computing.

The project demonstrates how the same image processing operations can be implemented using:

- standard C++ execution
- MPI process-level parallelism
- CUDA GPU parallelism

## Documentation

Additional project documentation is available here:

[Project Documentation](https://docs.google.com/document/d/1ZgULvbeOly2_cz59IIv4VbZ2RptbPkMEt235mdTk-kE/edit)
