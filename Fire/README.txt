HOW TO USE THIS TEMPLATE
========================

1. Copy the whole "WebGLTemplates" folder into your Unity project's
   "Assets" folder, so you end up with:

       Assets/WebGLTemplates/FixedTemplate/index.html
       Assets/WebGLTemplates/FixedTemplate/TemplateData/style.css
       Assets/WebGLTemplates/FixedTemplate/TemplateData/... (icons, see below)

2. COPY THESE 6 IMAGE FILES into the TemplateData folder above.
   I can't generate Unity's actual branded icon/logo images, so grab
   them from any WebGL build you've already made (they're the same
   in every Unity project — just copy-paste them):

       favicon.ico
       unity-logo-dark.png
       progress-bar-empty-dark.png
       progress-bar-full-dark.png
       webgl-logo.png
       fullscreen-button.png

   These live in your existing build's own TemplateData folder, e.g.
   the folder where your original index.html/style.css came from.

   Note: the game will still run fine even without these — you'd
   just see a missing loading-bar graphic and a blank favicon tab
   icon until you add them. Nothing will break.

3. In Unity: Edit > Project Settings > Player > WebGL tab >
   Resolution and Presentation > WebGL Template > select "FixedTemplate".

4. Build normally (File > Build Settings > Build). Unity will now pull
   index.html and style.css from this folder on every build automatically,
   filling in the correct build file names for you. You never need to
   manually edit index.html/style.css again.

WHAT WAS FIXED
===============
- style.css: canvas and container now use 100% width/height with
  position: fixed, instead of a hardcoded 1920x1080 box centered with
  a transform — this was what caused cropping on smaller laptop screens.
- index.html: added a resizeCanvas() function that keeps the canvas
  sized to the actual browser window on desktop, and listens for
  window resize events.
- index.html: replaced hardcoded build file names (test1/test2, etc.)
  with Unity's template macros ({{{ LOADER_FILENAME }}}, etc.) so this
  template works for ANY build name without editing, forever.
