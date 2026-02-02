# Timeline HTML - Quick Edit Guide

## Structure

The `timeline.html` file has **3 main sections** you'll edit:

### 1. **Slides Data** (Lines ~480-1750)
This is where all the content lives. Each week is a separate slide object.

```javascript
// Search for: "const slides = ["

const slides = [
    // Week 1
    {
        title: "Week 1 (Jan 15-21): Basic CSV Import",
        subtitle: "",
        content: `...`  // HTML content goes here
    },
    // Week 2
    {
        title: "Week 2 (Jan 22-28): Mapping & Import",
        ...
    },
    ...
]
```

### 2. **Navigation** (Lines ~1750-1800)
Side navigation structure - each section has a `firstSlide` property

```javascript
// Search for: "const navigationStructure = ["

const navigationStructure = [
    { type: 'section', title: 'Phase 1: Foundation', phase: 1, firstSlide: 2 },
    { type: 'slide', index: 2, title: 'Phase 1 Overview', section: 'phase1' },
    ...
]
```

**Note:** Phase headers are clickable and navigate to their `firstSlide`.

### 3. **Productboard Links** (Inside each week's content)
Links to Productboard features

```html
<!-- Search for: "📋 Productboard" -->

<div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-600">
    <h3 class="text-lg font-bold text-blue-800 mb-2">📋 Productboard</h3>
    <p class="text-sm text-gray-700">
        <a href="PASTE_URL_HERE" target="_blank" class="text-blue-600 hover:underline font-semibold">
            View Epic in Productboard →
        </a>
    </p>
</div>
```

## Common Edits

### Add/Update Productboard Link

1. **Find the week**: Search for `// ==================== WEEK N ====================`
2. **Find Productboard section**: Search for `📋 Productboard` within that week
3. **Update URL**: Replace the `href` value with the new Productboard URL

Example:
```html
<!-- BEFORE -->
<a href="" target="_blank">

<!-- AFTER -->
<a href="https://leanix.productboard.com/detail/MTpQbU..." target="_blank">
```

### Update Week Content

1. **Find the week**: Search for `// ==================== WEEK N ====================`
2. **Find the section to edit**:
   - **Problem Statement**: Look for `bg-purple-50`
   - **Requirements**: Look for `border-2 border-blue-500`
   - **Success Criteria**: Look for `bg-green-50`
   - **Out of Scope**: Look for `bg-orange-50`
   - **Sprint Review**: Look for `bg-teal-50`
3. **Edit the content**: Modify the text inside the `<p>` or `<li>` tags

### Change Week Title/Dates

Search for `title: "Week N (DATE_RANGE): TITLE"` and edit directly.

```javascript
// Example
title: "Week 1 (Jan 15-21): Basic CSV Import",  // Change this line
```

## Tips

- **Use your IDE's search** (`Cmd+F` or `Ctrl+F`) - all sections have clear markers
- **Week markers**: `// ==================== WEEK N ====================`
- **Each week is self-contained** - you won't accidentally edit the wrong week
- **Productboard links** always have the emoji `📋` - easy to find!
- **Backup before major edits**: `cp timeline.html timeline.html.backup`

## Quick Find Commands

```
Find Week 1:    // ==================== WEEK 1 ====================
Find Week 5:    // ==================== WEEK 5 ====================
Find all PB links: 📋 Productboard
Find navigation:   const navigation = [
Find slides start: const slides = [
```

## Example: Adding Week 4 Productboard Link

```bash
# 1. Search for Week 4
# Find: // ==================== WEEK 4 ====================

# 2. Scroll down to find Productboard section
# Find: 📋 Productboard

# 3. Update the href
# Change: <a href="" target="_blank">
# To:     <a href="https://leanix.productboard.com/detail/WEEK4_ID" target="_blank">

# Done! Refresh browser to see changes.
```

## File Locations

- Main file: `timeline.html` (optimized for editing)
- Data backup: `timeline-data.json` (reference only)
- This guide: `EDITING_GUIDE.md`
