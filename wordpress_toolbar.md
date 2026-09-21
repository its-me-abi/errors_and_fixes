below is code to add toolbar to wordpress self hosted.  
i am using wasmer.com with blockify theme

```html
<style>
  .simple-blog-nav {
    display: flex;
    gap: 6px;
    align-items: center;
    background-color: #d9ffc2;
    padding: 6px 8px;
    border-radius: 30px;
    overflow-x: auto;
    white-space: nowrap;
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
  .simple-blog-nav::-webkit-scrollbar {
    display: none;
  }
  .simple-blog-nav a {
    color: #1a4314;
    text-decoration: none;
    font-size: 13px;
    font-weight: 600;
    padding: 6px 14px;
    border-radius: 20px;
    transition: all 0.2s ease-in-out;
  }
  .simple-blog-nav a:hover,
  .simple-blog-nav a.active {
    background-color: #28601e;
    color: #ffffff;
  }
</style>
<p>
<nav class="simple-blog-nav"><a class="active" href="/">Home</a> <a href="/about">About Me</a> <a href="/projects">Projects</a> <a href="/blog">Blog</a></p></nav>

<script>
document.addEventListener("DOMContentLoaded", function() {
  // 1. Target correct selector (.simple-blog-nav instead of .blog-toolbar)
  var navLinks = document.querySelectorAll('.simple-blog-nav a');
  if (!navLinks.length) return;

  // Normalize current path (handles trailing slashes)
  var currentPath = window.location.pathname.replace(/\/$/, "");

  navLinks.forEach(function(link) {
    // Standardize link path
    var linkPath = new URL(link.href, window.location.origin).pathname.replace(/\/$/, "");

    // Check match for home ('') or specific pages
    var isMatch = (linkPath === currentPath) || (currentPath === "" && linkPath === "");

    if (isMatch) {
      link.classList.add('active');
    } else {
      link.classList.remove('active');
    }
  });
});
</script>
```
