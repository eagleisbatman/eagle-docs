---
name: api-spec-design
description: Create professional API specification documentation as HTML with brutalist styling. Includes endpoints, authentication, request/response schemas, error handling, and SDK examples. Outputs are desktop-optimized with one section per viewport. Use when user requests API documentation, API spec, REST API design, endpoint documentation, or OpenAPI spec visualization.
---

# API Specification Design Skill

**Author:** Gautam Mandewalker ([@eagleisbatman](https://github.com/eagleisbatman))

## Overview

Creates professional API specification documentation as HTML files with brutalist black-and-white aesthetics. Each section occupies one viewport with scroll-based navigation. Optimized for desktop/laptop viewing (1024px+).

## API Doc Structure (Required Sections)

1. **Overview** - Base URL, versioning, content types, headers
2. **Authentication** - Auth flow, token structure, refresh
3. **Common Patterns** - Pagination, filtering, sorting, errors
4. **Endpoints** - Grouped by resource (Auth, Users, etc.)
5. **Data Schemas** - Complete object definitions
6. **Error Handling** - Error codes, response formats
7. **Rate Limiting** - Limits by endpoint, headers
8. **SDK Examples** - Code samples per language

## HTTP Method Styling

| Method | Style |
|--------|-------|
| GET | White bg, black border |
| POST | Black bg, white text |
| PUT/PATCH | Gray bg |
| DELETE | White bg, dashed border |

## Complete Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[API Name] - API Documentation</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        :root {
            --black: #1a1a1a;
            --mid-gray: #666;
            --light-gray: #999;
            --border-gray: #ddd;
            --bg-gray: #f5f5f5;
            --white: #fff;
        }
        html { scroll-behavior: smooth; }
        body {
            font-family: 'IBM Plex Sans', sans-serif;
            font-size: 16px;
            line-height: 1.7;
            background: var(--bg-gray);
            color: var(--black);
        }
        
        /* Sidebar */
        .sidebar-nav {
            width: 300px;
            position: fixed;
            top: 0; left: 0;
            height: 100vh;
            background: var(--white);
            border-right: 3px solid var(--black);
            padding: 32px;
            overflow-y: auto;
            z-index: 100;
        }
        .doc-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 4px;
        }
        .doc-type {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: var(--mid-gray);
            margin-bottom: 24px;
            padding-bottom: 20px;
            border-bottom: 2px solid var(--black);
        }
        .nav-list { list-style: none; }
        .nav-link {
            display: block;
            padding: 10px 16px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            color: var(--black);
            text-decoration: none;
            border: 2px solid transparent;
            margin-bottom: 2px;
        }
        .nav-link:hover { background: var(--bg-gray); }
        .nav-link.active { background: var(--black); color: var(--white); }
        .nav-number { display: inline-block; width: 28px; font-weight: 600; }
        .nav-section-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--mid-gray);
            margin: 20px 0 8px 16px;
            padding-top: 16px;
            border-top: 1px solid var(--border-gray);
        }
        
        /* Main */
        .main-content { margin-left: 300px; }
        
        .api-section {
            min-height: 100vh;
            padding: 80px;
            border-bottom: 3px solid var(--black);
        }
        .api-section:nth-child(even) { background: var(--white); }
        .section-inner { max-width: 1000px; margin: 0 auto; }
        .section-number {
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            color: var(--mid-gray);
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 8px;
        }
        .section-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 32px;
            font-weight: 700;
            margin-bottom: 40px;
            padding-bottom: 16px;
            border-bottom: 4px solid var(--black);
        }
        
        /* Endpoint Card */
        .endpoint-card {
            background: var(--white);
            border: 2px solid var(--black);
            margin-bottom: 32px;
            box-shadow: 6px 6px 0 var(--black);
        }
        .endpoint-header {
            padding: 16px 24px;
            border-bottom: 2px solid var(--black);
            display: flex;
            align-items: center;
            gap: 16px;
        }
        .http-method {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            font-weight: 700;
            padding: 6px 12px;
            min-width: 70px;
            text-align: center;
            border: 2px solid var(--black);
        }
        .method-get { background: var(--white); }
        .method-post { background: var(--black); color: var(--white); }
        .method-put, .method-patch { background: var(--bg-gray); }
        .method-delete { background: var(--white); color: var(--mid-gray); border-style: dashed; }
        .endpoint-path {
            font-family: 'JetBrains Mono', monospace;
            font-size: 15px;
            font-weight: 600;
        }
        .endpoint-path .param { color: var(--mid-gray); }
        .endpoint-description {
            padding: 16px 24px;
            background: var(--bg-gray);
            border-bottom: 2px solid var(--black);
            font-size: 15px;
        }
        .endpoint-body { padding: 24px; }
        
        /* Code Blocks */
        .code-block-wrapper { border: 2px solid var(--black); margin: 16px 0; }
        .code-block-header {
            background: var(--black);
            color: var(--white);
            padding: 10px 16px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            font-weight: 600;
            display: flex;
            justify-content: space-between;
        }
        .code-block {
            background: #1a1a1a;
            color: #f5f5f5;
            padding: 20px;
            overflow-x: auto;
            font-family: 'JetBrains Mono', monospace;
            font-size: 13px;
            line-height: 1.6;
        }
        .status-badge {
            font-size: 10px;
            padding: 3px 8px;
            border: 1px solid var(--white);
        }
        
        /* Params Table */
        .params-section-title {
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin: 24px 0 12px 0;
            color: var(--mid-gray);
        }
        .params-table { width: 100%; border-collapse: collapse; }
        .params-table th {
            font-family: 'JetBrains Mono', monospace;
            font-size: 11px;
            text-transform: uppercase;
            text-align: left;
            padding: 12px;
            background: var(--black);
            color: var(--white);
            border: 2px solid var(--black);
        }
        .params-table td {
            padding: 12px;
            border: 2px solid var(--black);
            font-size: 14px;
            vertical-align: top;
        }
        .param-name { font-family: 'JetBrains Mono', monospace; font-weight: 600; }
        .param-type { font-family: 'JetBrains Mono', monospace; font-size: 12px; color: var(--mid-gray); display: block; margin-top: 4px; }
        .param-required {
            font-family: 'JetBrains Mono', monospace;
            font-size: 9px;
            font-weight: 700;
            padding: 2px 6px;
            background: var(--black);
            color: var(--white);
            margin-left: 6px;
        }
        .param-optional {
            font-family: 'JetBrains Mono', monospace;
            font-size: 9px;
            padding: 2px 6px;
            border: 1px solid var(--mid-gray);
            color: var(--mid-gray);
            margin-left: 6px;
        }
        
        /* Schema Definition */
        .schema-card {
            background: var(--white);
            border: 2px solid var(--black);
            margin-bottom: 24px;
        }
        .schema-header {
            background: var(--black);
            color: var(--white);
            padding: 14px 20px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 16px;
            font-weight: 700;
        }
        .schema-body { padding: 0; }
        .schema-field {
            display: grid;
            grid-template-columns: 180px 100px 1fr;
            padding: 12px 20px;
            border-bottom: 1px solid var(--border-gray);
            font-size: 14px;
        }
        .schema-field:last-child { border-bottom: none; }
        .field-name { font-family: 'JetBrains Mono', monospace; font-weight: 600; }
        .field-type { font-family: 'JetBrains Mono', monospace; font-size: 12px; color: var(--mid-gray); }
        
        /* Info Grid */
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 32px;
        }
        .info-card {
            border: 2px solid var(--black);
            padding: 20px;
            background: var(--white);
        }
        .info-label {
            font-family: 'JetBrains Mono', monospace;
            font-size: 10px;
            text-transform: uppercase;
            color: var(--mid-gray);
            margin-bottom: 8px;
        }
        .info-value {
            font-family: 'JetBrains Mono', monospace;
            font-size: 15px;
            font-weight: 600;
        }
        
        .icon { width: 20px; height: 20px; stroke-width: 2; }
    </style>
</head>
<body>
    <nav class="sidebar-nav">
        <div class="doc-title">[API Name]</div>
        <div class="doc-type">API Specification v2.0</div>
        <ul class="nav-list">
            <li><a href="#overview" class="nav-link"><span class="nav-number">01</span> Overview</a></li>
            <li><a href="#auth" class="nav-link"><span class="nav-number">02</span> Authentication</a></li>
            <li><a href="#patterns" class="nav-link"><span class="nav-number">03</span> Common Patterns</a></li>
            <div class="nav-section-title">Endpoints</div>
            <li><a href="#auth-endpoints" class="nav-link"><span class="nav-number">04</span> Auth</a></li>
            <li><a href="#user-endpoints" class="nav-link"><span class="nav-number">05</span> Users</a></li>
            <li><a href="#resource-endpoints" class="nav-link"><span class="nav-number">06</span> Resources</a></li>
            <div class="nav-section-title">Reference</div>
            <li><a href="#schemas" class="nav-link"><span class="nav-number">07</span> Schemas</a></li>
            <li><a href="#errors" class="nav-link"><span class="nav-number">08</span> Errors</a></li>
            <li><a href="#rate-limits" class="nav-link"><span class="nav-number">09</span> Rate Limits</a></li>
        </ul>
    </nav>

    <main class="main-content">
        <!-- Section: Overview -->
        <section id="overview" class="api-section">
            <div class="section-inner">
                <div class="section-number">Section 01</div>
                <h1 class="section-title">Overview</h1>
                
                <div class="info-grid">
                    <div class="info-card">
                        <div class="info-label">Base URL</div>
                        <div class="info-value">https://api.example.com/v1</div>
                    </div>
                    <div class="info-card">
                        <div class="info-label">Version</div>
                        <div class="info-value">2.0.0</div>
                    </div>
                    <div class="info-card">
                        <div class="info-label">Content-Type</div>
                        <div class="info-value">application/json</div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Section: Endpoints -->
        <section id="auth-endpoints" class="api-section">
            <div class="section-inner">
                <div class="section-number">Section 04</div>
                <h1 class="section-title">Authentication Endpoints</h1>
                
                <div class="endpoint-card">
                    <div class="endpoint-header">
                        <span class="http-method method-post">POST</span>
                        <span class="endpoint-path">/auth/otp/send</span>
                    </div>
                    <div class="endpoint-description">
                        Send OTP to phone number for authentication.
                    </div>
                    <div class="endpoint-body">
                        <div class="params-section-title">Request Body</div>
                        <table class="params-table">
                            <tr>
                                <th>Parameter</th>
                                <th>Type</th>
                                <th>Description</th>
                            </tr>
                            <tr>
                                <td>
                                    <span class="param-name">phone</span>
                                    <span class="param-required">Required</span>
                                    <span class="param-type">string</span>
                                </td>
                                <td><span class="param-type">string</span></td>
                                <td>Phone number with country code (e.g., +919876543210)</td>
                            </tr>
                        </table>
                        
                        <div class="params-section-title">Response</div>
                        <div class="code-block-wrapper">
                            <div class="code-block-header">
                                <span>Response</span>
                                <span class="status-badge">200 OK</span>
                            </div>
                            <pre class="code-block">{
  "success": true,
  "data": {
    "message": "OTP sent successfully",
    "expires_in": 300,
    "retry_after": 60
  }
}</pre>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Section: Schemas -->
        <section id="schemas" class="api-section">
            <div class="section-inner">
                <div class="section-number">Section 07</div>
                <h1 class="section-title">Data Schemas</h1>
                
                <div class="schema-card">
                    <div class="schema-header">User</div>
                    <div class="schema-body">
                        <div class="schema-field">
                            <span class="field-name">id</span>
                            <span class="field-type">UUID</span>
                            <span>Unique user identifier</span>
                        </div>
                        <div class="schema-field">
                            <span class="field-name">phone</span>
                            <span class="field-type">string</span>
                            <span>Phone number with country code</span>
                        </div>
                        <div class="schema-field">
                            <span class="field-name">name</span>
                            <span class="field-type">string?</span>
                            <span>Display name (optional)</span>
                        </div>
                        <div class="schema-field">
                            <span class="field-name">created_at</span>
                            <span class="field-type">datetime</span>
                            <span>Account creation timestamp</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            lucide.createIcons();
            
            // Active nav highlighting
            const sections = document.querySelectorAll('.api-section');
            const navLinks = document.querySelectorAll('.nav-link');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => link.classList.remove('active'));
                        const activeLink = document.querySelector(`a[href="#${entry.target.id}"]`);
                        if (activeLink) activeLink.classList.add('active');
                    }
                });
            }, { threshold: 0.3 });
            
            sections.forEach(section => observer.observe(section));
        });
    </script>
</body>
</html>
```

## Output Location
Save API spec files to: `/mnt/user-data/outputs/`
