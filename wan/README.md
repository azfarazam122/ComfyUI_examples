```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wan 2.1 Models Guide</title>
    <style>
        /* General Styles */
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f0f4f8;
            color: #333;
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }
        a {
            color: #007bff;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        a:hover {
            color: #0056b3;
            text-decoration: underline;
        }
        img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #007bff, #00c6ff);
            color: #fff;
            padding: 40px 20px;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        header h1 {
            margin: 0;
            font-size: 2.5em;
            font-weight: bold;
        }
        header p {
            font-size: 1.2em;
            margin: 10px 0 0;
        }

        /* Main Content */
        main {
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        section {
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            margin-bottom: 40px;
            padding: 20px;
        }
        h2 {
            color: #007bff;
            font-size: 2em;
            margin-bottom: 20px;
            border-bottom: 2px solid #007bff;
            padding-bottom: 5px;
        }
        h3 {
            color: #333;
            font-size: 1.5em;
            margin-top: 30px;
        }

        /* Table of Contents */
        #toc {
            background: #e9ecef;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 40px;
        }
        #toc ul {
            list-style: none;
            padding: 0;
        }
        #toc li {
            margin-bottom: 10px;
        }
        #toc a {
            font-weight: bold;
        }

        /* Tables */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }
        th {
            background-color: #007bff;
            color: #fff;
        }
        tr:hover {
            background-color: #f1f1f1;
        }

        /* Workflow Examples */
        .workflow-example {
            margin-top: 20px;
            text-align: center;
        }
        .workflow-example img {
            border: 1px solid #ddd;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        .workflow-example p {
            font-style: italic;
            color: #666;
            margin-top: 10px;
        }

        /* Footer */
        footer {
            background: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
            position: relative;
            bottom: 0;
            width: 100%;
        }
        footer p {
            margin: 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>Wan 2.1 Models</h1>
        <p>Welcome to the Wan 2.1 Models guide! Unleash your creativity with state-of-the-art video generation.</p>
    </header>

    <main>
        <section id="toc">
            <h2>Table of Contents</h2>
            <ul>
                <li><a href="#files-to-download">Files to Download</a></li>
                <li><a href="#workflows">Workflows</a></li>
            </ul>
        </section>

        <section id="files-to-download">
            <h2>Files to Download</h2>
            <p>Get started by downloading these files and placing them in the correct folders within your ComfyUI setup.</p>

            <h3>Text Encoder and VAE</h3>
            <p>These are the building blocks for Wan 2.1 models—essential for proper operation.</p>
            <table>
                <thead>
                    <tr>
                        <th>File Name</th>
                        <th>Download Link</th>
                        <th>Destination Folder</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><code>umt5_xxl_fp8_e4m3fn_scaled.safetensors</code></td>
                        <td><a href="https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/tree/main/split_files/text_encoders" target="_blank">Download</a></td>
                        <td><code>ComfyUI/models/text_encoders/</code></td>
                    </tr>
                    <tr>
                        <td><code>wan_2.1_vae.safetensors</code></td>
                        <td><a href="https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/vae/wan_2.1_vae.safetensors" target="_blank">Download</a></td>
                        <td><code>ComfyUI/models/vae/</code></td>
                    </tr>
                </tbody>
            </table>

            <h3>Video Models</h3>
            <p>The heart of Wan 2.1 video generation. Download them <a href="https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/tree/main/split_files/diffusion_models" target="_blank">here</a> and place them in: <code>ComfyUI/models/diffusion_models/</code></p>
            <p><strong>Note:</strong> Examples use 16-bit models for best performance. Opt for fp8 versions if memory is tight.</p>
        </section>

        <section id="workflows">
            <h2>Workflows</h2>
            <p>Dive into video creation with these workflows. Load the JSON files into ComfyUI to begin.</p>

            <h3>Text to Video</h3>
            <p>Turn your words into stunning videos with this workflow.</p>
            <ul>
                <li><strong>Required File:</strong> <a href="https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/diffusion_models/wan2.1_t2v_1.3B_fp16.safetensors" target="_blank"><code>wan2.1_t2v_1.3B_fp16.safetensors</code></a> (Place in: <code>ComfyUI/models/diffusion_models/</code>). Works with the 14B model too!</li>
                <li><strong>Download Workflow:</strong> <a href="text_to_video_wan.json" target="_blank">Workflow in JSON format</a></li>
            </ul>
            <div class="workflow-example">
                <img src="text_to_video_wan.webp" alt="Text to Video Workflow Example">
                <p>See the Text to Video workflow in action!</p>
            </div>

            <h3>Image to Video</h3>
            <p>Bring static images to life with this dynamic workflow.</p>
            <ul>
                <li><strong>Required Files:</strong>
                    <ul>
                        <li><a href="https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/diffusion_models/wan2.1_i2v_480p_14B_bf16.safetensors" target="_blank"><code>wan2.1_i2v_480p_14B_bf16.safetensors</code></a> (Place in: <code>ComfyUI/models/diffusion_models/</code>)</li>
                        <li><a href="https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/clip_vision/clip_vision_h.safetensors" target="_blank"><code>clip_vision_h.safetensors</code></a> (Place in: <code>ComfyUI/models/clip_vision/</code>)</li>
                    </ul>
                </li>
                <li><strong>Details:</strong> Outputs 33 frames at 512x512. Need more frames or 720p? Make sure your hardware’s up for it!</li>
                <li><strong>Download Workflow:</strong> <a href="image_to_video_wan_example.json" target="_blank">Workflow in JSON format</a></li>
            </ul>
            <div class="workflow-example">
                <img src="image_to_video_wan_example.webp" alt="Image to Video Workflow Example at 512x512">
                <p>Image to Video workflow at 512x512 resolution.</p>
            </div>
            <div class="workflow-example">
                <img src="image_to_video_wan_720p_example.webp" alt="Image to Video Workflow Example at 720p">
                <p>Same example at 720p—perfect for high-end setups!</p>
            </div>
        </section>
    </main>

    <footer>
        <p>Happy video generating with Wan 2.1!</p>
    </footer>
</body>
</html>
