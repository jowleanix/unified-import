# HTML Templates for Timeline Edits

## Week Slide Template

Copy and paste this template when adding a new week:

```javascript
            // ==================== WEEK N ====================
            {
                title: "Week N (DATE RANGE): TITLE HERE",
                subtitle: "",
                content: `
                    <div class="space-y-4">
                        <div class="bg-purple-50 p-4 rounded-lg">
                            <h3 class="text-lg font-bold text-purple-800 mb-2">Problem Statement (and Value Proposition)</h3>
                            <p class="text-gray-700">PROBLEM STATEMENT HERE</p>
                        </div>

                        <div class="bg-white p-4 rounded-lg border-2 border-blue-500">
                            <h3 class="text-lg font-bold text-blue-800 mb-2">Key Functionality (Requirements)</h3>
                            <ul class="space-y-2 text-gray-700">
                                <li>• Requirement 1</li>
                                <li>• Requirement 2</li>
                                <li>• Requirement 3</li>
                            </ul>
                        </div>

                        <div class="bg-green-50 p-4 rounded-lg">
                            <h3 class="text-lg font-bold text-green-800 mb-2">Success Criteria</h3>
                            <p class="text-gray-700">→ SUCCESS CRITERIA HERE</p>
                        </div>

                        <div class="bg-orange-50 p-4 rounded-lg">
                            <h3 class="text-lg font-bold text-orange-800 mb-2">Limitations/Out of Scope</h3>
                            <ul class="space-y-1 text-sm text-gray-700">
                                <li>• Out of scope item 1</li>
                                <li>• Out of scope item 2</li>
                                <li>• Out of scope item 3</li>
                            </ul>
                        </div>

                        <div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-600">
                            <h3 class="text-lg font-bold text-blue-800 mb-2">📋 Productboard</h3>
                            <p class="text-sm text-gray-700">
                                <a href="PRODUCTBOARD_URL_HERE" target="_blank" class="text-blue-600 hover:underline font-semibold">
                                    View Epic in Productboard →
                                </a>
                            </p>
                        </div>
                    </div>
                `
            },
```

## Productboard Link Only

If a week already exists and you just need to add the Productboard link:

```html
<div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-600">
    <h3 class="text-lg font-bold text-blue-800 mb-2">📋 Productboard</h3>
    <p class="text-sm text-gray-700">
        <a href="PASTE_PRODUCTBOARD_URL_HERE" target="_blank" class="text-blue-600 hover:underline font-semibold">
            View Epic in Productboard →
        </a>
    </p>
</div>
```

Insert this **before** the closing `</div>` of the week's content section.

## Sprint Review Script Template

Add this section between "Success Criteria" and "Out of Scope":

```html
<div class="bg-teal-50 p-4 rounded-lg border-l-4 border-teal-500">
    <h3 class="text-lg font-bold text-teal-800 mb-2">🎬 Sprint Review Script</h3>
    <div class="space-y-3 text-sm text-gray-700">
        <div>
            <p class="font-semibold text-gray-800">Demo Flow:</p>
            <ol class="ml-4 mt-1 space-y-1">
                <li>1. Step one of the demo</li>
                <li>2. Step two of the demo</li>
                <li>3. Step three of the demo</li>
            </ol>
        </div>
        <div>
            <p class="font-semibold text-gray-800">Key Talking Points:</p>
            <ul class="ml-4 mt-1 space-y-1">
                <li>• Talking point 1</li>
                <li>• Talking point 2</li>
                <li>• Talking point 3</li>
            </ul>
        </div>
    </div>
</div>
```

## Phase Divider Template

For adding phase separator slides:

```javascript
            {
                title: "Phase N: PHASE NAME",
                subtitle: "Weeks X-Y | DESCRIPTION",
                content: `
                    <div class="flex flex-col items-center justify-center h-full">
                        <div class="text-center mb-8">
                            <h1 class="text-5xl font-bold text-blue-600 mb-4">Phase N: PHASE NAME</h1>
                            <h2 class="text-3xl text-gray-700 mb-6">Weeks X-Y</h2>
                            <p class="text-xl text-gray-600">SHORT DESCRIPTION</p>
                        </div>
                        <div class="bg-purple-50 p-8 rounded-lg max-w-3xl">
                            <p class="text-2xl font-semibold text-purple-800 mb-4">Goal</p>
                            <p class="text-xl text-gray-700">PHASE GOAL HERE</p>
                        </div>
                    </div>
                `
            },
```

## Color Reference

Use these classes for consistent styling:

- **Problem Statement**: `bg-purple-50` + `text-purple-800`
- **Requirements**: `bg-white border-2 border-blue-500` + `text-blue-800`
- **Success Criteria**: `bg-green-50` + `text-green-800`
- **Sprint Review**: `bg-teal-50 border-l-4 border-teal-500` + `text-teal-800`
- **Out of Scope**: `bg-orange-50` + `text-orange-800`
- **Productboard**: `bg-blue-50 border-l-4 border-blue-600` + `text-blue-800`
- **Visuals/URLs**: `bg-gray-50` + `text-gray-800`

## Quick Copy-Paste Examples

### Just Requirements
```html
<ul class="space-y-2 text-gray-700">
    <li>• Requirement 1</li>
    <li>• Requirement 2</li>
</ul>
```

### Just Out of Scope
```html
<ul class="space-y-1 text-sm text-gray-700">
    <li>• Out of scope item 1</li>
    <li>• Out of scope item 2</li>
</ul>
```

### Link Button
```html
<a href="URL" target="_blank" class="text-blue-600 hover:underline font-semibold">
    Link Text →
</a>
```
