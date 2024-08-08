### README.md

# Video Transcoding and Streaming with Docker, FFmpeg, and AWS S3

This README provides detailed instructions for setting up a video transcoding and streaming workflow using Docker, FFmpeg, Node.js, and AWS S3. It covers creating an S3 bucket, writing a Dockerfile, transcoding video into HLS segments, and using Video.js for playback.

## Table of Contents
1. [Dockerfile for Transcoding](#dockerfile-for-transcoding)
2. [Running the Docker Container](#running-the-docker-container)
3. [Transcoding Command](#transcoding-command)
4. [Using Video.js for Playback](#using-videojs-for-playback)



## Dockerfile

1. **Check the dockerfile in the repository**

## Running the Docker Container

** 
docker build -t video-transcoder .
docker run -it -v "D:/OWN WORK/httpLiveStreaming/hls/video:/home/app/videos" video-transcoder
**

## Transcoding Commands
** Check commands.txt in repo

## Full Workflow
1. Create S3 Bucket and Configure CORS: Ensure your S3 bucket is ready for cross-origin requests.
2. Write Dockerfile: Create a Dockerfile that installs Node.js and FFmpeg on an Ubuntu Focal base image.
3. Run Docker Container: Build and run the Docker container, mounting your local directories for input and output.
4. Transcode Video: Inside the Docker container, use FFmpeg to transcode the video into 360p, 720p, and 1080p resolutions, creating HLS segments and playlists.
5. Create Master Playlist: Generate a master playlist that references all resolution playlists.
6. Upload to S3: Sync the generated HLS files to your S3 bucket.
Setup Video.js: Create an HTML file that uses Video.js to play the video from the S3 bucket.

