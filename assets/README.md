## Assets Folder

This folder contains all media assets for the portfolio website.

### Required Files:

#### Videos
- `hero-bg.mp4` - Hero section background video (1920x1080, max 10MB)
- `project1-preview.mp4` through `project6-preview.mp4` - Portfolio video previews (720p, 5-10 seconds each)

#### Images
- `profile.jpg` - Your professional photo (800x800 or larger)
- `project1.jpg` through `project6.jpg` - Project thumbnail images (1280x720, 16:9 ratio)

### Tips for Adding Your Media:

1. **Compress videos** before uploading:
   ```bash
   # Using FFmpeg to compress video
   ffmpeg -i input.mp4 -c:v libx264 -crf 28 -c:a aac -b:a 128k output.mp4
   ```

2. **Optimize images**:
   - Use online tools like TinyPNG or ImageOptim
   - Save as JPG with 80-85% quality
   - Maintain 16:9 aspect ratio for thumbnails

3. **File naming**:
   - Use lowercase
   - No spaces (use hyphens instead)
   - Be consistent with numbering

### Placeholder Sources:

If you don't have content yet, you can use:
- **Pexels Videos**: https://www.pexels.com/videos/
- **Unsplash**: https://unsplash.com/
- **Pixabay**: https://pixabay.com/

Remember to replace all placeholders with your actual work before going live!
