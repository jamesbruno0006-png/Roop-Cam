# Roop-Cam

Take a video and replace the face in it with a face of your choice. You only need one image of the desired face. No dataset, no training.

This project is based on [roop-cam](https://github.com/hacksider/roop-cam) with additional tweaks, simplified installation process, and support for multiple platforms including CPU, NVIDIA, and AMD GPUs.

## Features

- Real-time face swapping in videos
- Single image face replacement
- Multiple platform support (CPU, NVIDIA CUDA, AMD DirectML)
- Webcam support for live face swapping
- GUI and CLI modes
- Face enhancement capabilities

## Disclaimer

This software is meant to be a productive contribution to the rapidly growing AI-generated media industry. It will help artists with tasks such as animating a custom character or using the character as a model for clothing etc.

The developers of this software are aware of its possible unethical applications and are committed to take preventative measures against them. It has a built-in check which prevents the program from working on inappropriate media including but not limited to nudity, graphic content, sensitive material such as war footage etc.

**Users of this software are expected to use this software responsibly while abiding by local law.** If the face of a real person is being used, users are suggested to get consent from the concerned person and clearly mention that it is a deepfake when posting content online. Developers of this software will not be responsible for actions of end-users.

## Requirements

### All Platforms
- Python 3.10 ([Download](https://www.python.org/ftp/python/3.10.11/python-3.10.11-amd64.exe))
- Git ([Download](https://github.com/git-for-windows/git/releases/download/v2.41.0.windows.1/Git-2.41.0-64-bit.exe))
- Visual Studio ([Download](https://visualstudio.microsoft.com/vs/community/))
- FFmpeg ([Download](https://github.com/BtbN/FFmpeg-Builds/releases))

### NVIDIA GPU (CUDA)
- CUDA Toolkit 11.8 ([Download](https://developer.nvidia.com/cuda-11-8-0-download-archive))
- cuDNN for CUDA 11.8 ([Download](https://developer.nvidia.com/downloads/compute/cudnn/secure/8.9.1/local_installers/11.8/cudnn-windows-x86_64-8.9.1.23_cuda11-archive.zip/))

## Installation

### Basic Installation (CPU)

1. Clone this repository:
```bash
git clone https://github.com/jamesbruno0006-png/Roop-Cam.git
cd Roop-Cam
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

### NVIDIA GPU Installation

1. Follow the basic installation steps above
2. Install CUDA Toolkit 11.8
3. Download and extract cuDNN
4. Copy cuDNN files from `bin` folder to `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\bin`
5. Run the CUDA setup script:
```bash
start_cuda.bat
```

### AMD/Intel GPU Installation (DirectML)

1. Follow the basic installation steps above
2. Install DirectML dependencies:
```bash
pip install -r requirements_dml.txt
```
3. Run the DirectML setup script:
```bash
start_dml.bat
```

## Usage

### GUI Mode

Run the application with GUI:
```bash
python run.py
```

This will launch a graphical interface where you can:
1. Select a source image (face you want to use)
2. Select a target video or image (where you want to replace the face)
3. Choose output location
4. Click "Start" to begin processing

### CLI Mode

Run from command line with arguments:
```bash
python run.py -s source.jpg -t target.mp4 -o output.mp4
```

### Command Line Arguments

```
options:
  -h, --help            show this help message and exit
  -s SOURCE_PATH, --source SOURCE_PATH
                        select a source image
  -t TARGET_PATH, --target TARGET_PATH
                        select a target image or video
  -o OUTPUT_PATH, --output OUTPUT_PATH
                        select output file or directory
  --frame-processor {face_swapper,face_enhancer} [{face_swapper,face_enhancer} ...]
                        pipeline of frame processors
  --keep-fps            keep original fps
  --keep-audio          keep original audio
  --keep-frames         keep temporary frames
  --many-faces          process every face
  --video-encoder {libx264,libx265,libvpx-vp9}
                        adjust output video encoder
  --video-quality VIDEO_QUALITY
                        adjust output video quality
  --max-memory MAX_MEMORY
                        maximum amount of RAM in GB
  --execution-provider {cpu,...} [{cpu,...} ...]
                        execution provider
  --execution-threads EXECUTION_THREADS
                        number of execution threads
  -v, --version         show program's version number and exit
```

## First Run

When you run this program for the first time, it will download required models (~300MB in size).

## Advanced Usage

For webcam and live streaming features, check the documentation in the `roop` directory.

For advanced configuration options, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Project Structure

```
Roop-Cam/
├── roop/              # Core application modules
│   ├── core.py        # Main processing logic
│   ├── ui.py          # User interface
│   ├── processors/    # Face processing modules
│   └── ...
├── run.py             # Main entry point
├── requirements.txt   # Python dependencies
├── start_cuda.bat     # NVIDIA GPU launch script
├── start_dml.bat      # AMD/Intel GPU launch script
└── README.md          # This file
```

## Credits

- [s0md3v/roop](https://github.com/s0md3v/roop) - Original roop project
- [hacksider/roop-cam](https://github.com/hacksider/roop-cam) - Webcam features
- [neurogen-dev/roop-neurogen](https://github.com/neurogen-dev/roop-neurogen) - Russian localization and improvements
- [henryruhs](https://github.com/henryruhs) - Major contributions
- [ffmpeg](https://ffmpeg.org/) - Video processing
- [deepinsight/insightface](https://github.com/deepinsight/insightface) - Face analysis models

## License

This project is licensed under the terms specified in [LICENSE](LICENSE).

## Support

For issues and questions:
- Check existing issues on GitHub
- Review the documentation
- Create a new issue with detailed information

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.
