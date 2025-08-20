# Project Thumbnails

## Current Setup
The projects are currently using placeholder images from placeholder.com. This allows you to see the thumbnail functionality immediately.

## To Use Local Images:
1. Place your project thumbnail images in this directory with the following names:
   - `ecommerce.jpg` - E-Commerce Website thumbnail
   - `task-management.jpg` - Task Management App thumbnail  
   - `cms.jpg` - CMS Website thumbnail
   - `portfolio.jpg` - Portfolio Website thumbnail
   - `budget.jpg` - Planning Budget thumbnail
   - `lms.jpg` - Learning Management System thumbnail

2. Update the `thumbnail` paths in `src/components/Projects.vue` from URLs to:
   ```javascript
   thumbnail: require('@/assets/thumbnails/ecommerce.jpg')
   ```

## Image Requirements:
- Format: JPG, PNG, or WEBP
- Recommended size: 400x300px or similar aspect ratio
- File size: Keep under 500KB for better performance

## Current Placeholder URLs:
The code currently uses placeholder.com URLs that match each project's color scheme. You can replace these with your actual project screenshots when ready.
