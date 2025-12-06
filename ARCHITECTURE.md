# Portfolio Video Delivery Architecture

This document outlines the architecture for delivering video content for your portfolio using Fastly CDN and Object Storage. This is a **Progressive Download** architecture, which is sufficient and efficient for portfolio use cases, avoiding the complexity of full adaptive bitrate streaming.

## Architecture Diagram

## Architecture Diagram

```text
[Visitor's Browser]
       |
       | 1. Request Page (index.html)
       v
[Portfolio Host] (Netlify/Vercel)
       |
       | 2. Return HTML + Video URL
       v
[Visitor's Browser]
       |
       | 3. Request Video (video.mp4)
       v
[Fastly CDN Edge] <----(4. Fetch if not cached)---- [Fastly Object Storage]
       |                                                 (Origin)
       | 5. Deliver Stream (Progressive Download)
       v
[Visitor's Browser] (Playback starts immediately)
```

## How it works (Step-by-Step Explanation)

1.  **The HTML:** Your `index.html` (hosted on your current provider, e.g., Netlify) contains a `<video>` tag pointing to the URL of your video hosted on Fastly.
    *   **Example Video URL:** `https://cdn.yourdomain.com/videos/project-showcase.mp4`
2.  **The Request:** When a visitor's browser loads your portfolio page, it encounters the `<video>` tag and initiates a request for the video file from the specified URL.
3.  **The Fastly CDN (Edge Caching):**
    *   **Initial Request (Cache Miss):** The first time a specific video is requested, or if the cached version has expired, the Fastly CDN will not have the file in its local cache. It will then fetch the video *once* from your Fastly Object Storage (the origin).
    *   **Subsequent Requests (Cache Hit):** After the initial fetch, the Fastly CDN caches the video file at its edge servers. Subsequent requests for the same video from users geographically close to that edge server will be served directly from the CDN's cache, providing very fast delivery and reducing the load on your origin storage.
4.  **Fastly Object Storage (Origin):** This is where your actual video files are permanently stored. It acts as the reliable source for the Fastly CDN.
5.  **The Playback (Progressive Download):** Because your MP4 video files are properly **"Web Optimized" (Fast Start)**, the browser can begin playing the video almost immediately, even before the entire file has been downloaded. This provides a smooth user experience without long buffering delays.

## Implementation Details for Your Portfolio

**Recommended: Direct Video Tag**

This method offers the best control over the video player's styling and responsiveness within your `index.html`.

```html
<video controls preload="metadata" width="100%" height="auto">
  <!-- Replace [YOUR-FASTLY-DOMAIN] with your actual Fastly domain -->
  <source src="https://[YOUR-FASTLY-DOMAIN]/my-portfolio-video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

**Key Considerations:**

*   **Video Optimization:** Ensure your `.mp4` files are encoded with **H.264 video** and **AAC audio**, and are **"Web Optimized" (Fast Start)**. Tools like Handbrake can do this easily.
*   **File Size:** Keep video file sizes reasonable (e.g., under 50MB for short clips) to ensure quick downloads, especially for users on slower connections.
*   **Domain:** Replace `[YOUR-FASTLY-DOMAIN]` with the actual domain you have configured for your Fastly CDN service, which points to your Fastly Object Storage bucket.