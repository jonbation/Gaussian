# Gauss 
 
A Stable Diffusion app for ML models.

## Usage

- Gaussian is document-based. To get started, create a new document.
  - All the images you generate are stored locally inside your `.gaussnb` (Gauss Notebook) files.
  - If it's your first time using Gauss, you'll need to install Stable Diffusion models to start generating images. Each model is about 2.5gb.
- Write prompt text and adjust parameters in the composer view at the bottom of the document window.


## Project Status

This software is under development and is alpha quality. Builds are available on the [releases] page.

Alternatives:

- is a Stable Diffusion UI built with Electron & Python. It's probably slower than Gauss but has many more features.

### System requirements

- macOS 13.1+
- Xcode 14.2+
- `git-lfs` is used to fetch pre-built models from HuggingFace.
  - If you have `brew`: `brew install git-lfs`, then `git lfs install`.
  - Otherwise, [download the installer here](https://git-lfs.com/), then `git lfs install`.
- At least 10gb of free disk space.
- Recommended: [set up Xcode to format code when you save](https://luisramos.dev/xcode-format-and-save).

### Building Gauss

1. Clone this repo: `git clone https://github.com/justjake/Gauss`
1. Open the project file (Gauss.xcodeproj) with Xcode: `open Gauss.xcodeproj`
1. You should be able to run (Cmd-R) the project.


### Adding or updating models

To release model data, we pack the models into archive files, split the archive files into parts no larger than 2gb, and then publish everything via Github release.

We use Apple Archive (.aar) format instead of something common like Zip because .aar unpacking is available from built-in libraries, and zip is not.

1. To create the `.aar` files: `make aars`
1. Serve the newly-built .aar files locally: `make serve`
1. Switch to installing models locally:
1. Run the project in Xcode, then open the Models window (Window > Models).
1. Open the "Advanced" dropdown and choose "Custom Host"
1. Remove existing model files: `make uninstall-models`
