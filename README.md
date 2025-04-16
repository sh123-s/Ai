# AI & Content Tools - Professional Web App

Here's a responsive web application that meets your requirements with a dark hacker-style theme, video upload functionality, and SEO optimization tools.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="AI-powered content tools for YouTube, Facebook, Instagram, and SEO. Generate optimized titles, thumbnails, descriptions, and tags for your videos. Digital marketing tools for content creators.">
    <title>AI & Content Tools | Website Performance | SEO & Digital Marketing Tools</title>
    <style>
        :root {
            --primary: #00ff41;
            --secondary: #008f11;
            --dark: #0d0208;
            --darker: #003b00;
            --light: #e0e0e0;
            --danger: #ff0038;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Courier New', monospace;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            line-height: 1.6;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            padding: 20px 0;
            border-bottom: 1px solid var(--secondary);
            margin-bottom: 30px;
        }
        
        .logo {
            font-size: 2rem;
            color: var(--primary);
            text-shadow: 0 0 5px var(--primary);
            margin-bottom: 10px;
        }
        
        .tagline {
            color: var(--secondary);
            font-size: 1.2rem;
        }
        
        .main-title {
            text-align: center;
            margin: 30px 0;
            color: var(--primary);
            font-size: 2.5rem;
            text-shadow: 0 0 10px var(--primary);
        }
        
        .tool-container {
            background-color: var(--darker);
            border: 1px solid var(--secondary);
            border-radius: 5px;
            padding: 20px;
            margin-bottom: 30px;
            box-shadow: 0 0 15px rgba(0, 255, 65, 0.1);
        }
        
        .tool-title {
            color: var(--primary);
            margin-bottom: 20px;
            font-size: 1.5rem;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            color: var(--secondary);
        }
        
        input, select, textarea {
            width: 100%;
            padding: 12px;
            background-color: rgba(0, 0, 0, 0.5);
            border: 1px solid var(--secondary);
            color: var(--light);
            border-radius: 4px;
            font-size: 1rem;
        }
        
        textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        .btn {
            background-color: var(--primary);
            color: var(--dark);
            border: none;
            padding: 12px 24px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            border-radius: 4px;
            transition: all 0.3s;
            text-transform: uppercase;
        }
        
        .btn:hover {
            background-color: var(--secondary);
            box-shadow: 0 0 15px var(--primary);
        }
        
        .btn-danger {
            background-color: var(--danger);
        }
        
        .btn-danger:hover {
            box-shadow: 0 0 15px var(--danger);
        }
        
        .result-container {
            margin-top: 30px;
            display: none;
        }
        
        .result-box {
            background-color: rgba(0, 0, 0, 0.3);
            border: 1px solid var(--secondary);
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 4px;
            position: relative;
        }
        
        .result-title {
            color: var(--primary);
            margin-bottom: 10px;
        }
        
        .copy-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--darker);
            color: var(--primary);
            border: 1px solid var(--primary);
            padding: 5px 10px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.8rem;
        }
        
        .copy-btn:hover {
            background-color: var(--primary);
            color: var(--dark);
        }
        
        footer {
            margin-top: 50px;
            padding: 30px 0;
            border-top: 1px solid var(--secondary);
            text-align: center;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .footer-links a {
            color: var(--secondary);
            text-decoration: none;
        }
        
        .footer-links a:hover {
            color: var(--primary);
            text-decoration: underline;
        }
        
        .scroll-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: var(--primary);
            color: var(--dark);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            opacity: 0;
            transition: all 0.3s;
            font-size: 1.5rem;
        }
        
        .scroll-top.visible {
            opacity: 1;
        }
        
        @media (max-width: 768px) {
            .main-title {
                font-size: 2rem;
            }
            
            .footer-links {
                flex-direction: column;
                gap: 10px;
            }
        }
        
        /* Matrix animation background */
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
            pointer-events: none;
        }
    </style>
</head>
<body>
    <div class="matrix-bg" id="matrixCanvas"></div>
    
    <div class="container">
        <header>
            <div class="logo">AI & Content Tools</div>
            <div class="tagline">Website Performance | SEO & Digital Marketing Tools</div>
        </header>
        
        <h1 class="main-title">AI-Powered Content Optimization Suite</h1>
        
        <div class="tool-container">
            <h2 class="tool-title">Video Content Analyzer</h2>
            
            <div class="form-group">
                <label for="video-upload">Upload Your Video</label>
                <input type="file" id="video-upload" accept="video/*">
            </div>
            
            <div class="form-group">
                <label for="video-category">Select Category</label>
                <select id="video-category">
                    <option value="">-- Select a Category --</option>
                    <option value="education">Education</option>
                    <option value="entertainment">Entertainment</option>
                    <option value="gaming">Gaming</option>
                    <option value="technology">Technology</option>
                    <option value="lifestyle">Lifestyle</option>
                    <option value="business">Business</option>
                    <option value="music">Music</option>
                    <option value="sports">Sports</option>
                    <option value="other">Other</option>
                </select>
            </div>
            
            <button id="analyze-btn" class="btn">Generate Optimized Content</button>
            
            <div class="result-container" id="result-container">
                <h3 class="result-title">Optimized Content for Your Video</h3>
                
                <div class="result-box">
                    <h4>Title Suggestions</h4>
                    <p id="title-result">Loading...</p>
                    <button class="copy-btn" onclick="copyToClipboard('title-result')">Copy</button>
                </div>
                
                <div class="result-box">
                    <h4>Thumbnail Ideas</h4>
                    <p id="thumbnail-result">Loading...</p>
                    <button class="copy-btn" onclick="copyToClipboard('thumbnail-result')">Copy</button>
                </div>
                
                <div class="result-box">
                    <h4>Description</h4>
                    <p id="description-result">Loading...</p>
                    <button class="copy-btn" onclick="copyToClipboard('description-result')">Copy</button>
                </div>
                
                <div class="result-box">
                    <h4>Tags</h4>
                    <p id="tags-result">Loading...</p>
                    <button class="copy-btn" onclick="copyToClipboard('tags-result')">Copy</button>
                </div>
                
                <div class="result-box">
                    <h4>SEO Optimized Content</
