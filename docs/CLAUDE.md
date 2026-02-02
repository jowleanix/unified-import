# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Inventory Builder Rebuild - Timeline** is a sprint planning and documentation project, not a traditional software application. It tracks an 11-week rebuild effort for LeanIX's Inventory Builder feature, with a goal of 5 customers using the product by March 31, 2025.

This repository serves as a central hub for:
- Interactive sprint timeline visualization (timeline.html)
- Feature requirements tracking and completion status
- Strategic analysis and sprint planning
- Integration with Productboard for feature/requirement management

## Project Files

### Core Deliverables
- **timeline.html** (128KB) - Interactive sprint planning presentation with all 11 weeks and feature checklist. Self-contained with embedded CSS and JavaScript. Opens directly in any browser.
- **timeline.md** - Markdown version of the sprint plan (for reference)
- **feature-checklist.json** - 35 tracked features with priority levels and completion tracking

### Configuration & Data
- **timeline-data.json** - Structured metadata including project info, 11 steps with titles/dates, and Productboard URLs
- **data.json** - Productboard insights (auto-generated from export)
- **data/** - Productboard export in JSONL format (2.7MB+ of notes and metadata)
- **.env** - Jira/Productboard credentials (in .gitignore)

### Documentation
- **README.md** - Quick overview of files and usage
- **EDITING_GUIDE.md** - Detailed guide for editing timeline.html with search markers and examples
- **TIMELINE_ANALYSIS.md** - Strategic analysis identifying feature distribution issues and recommendations
- **TEMPLATES.md** - HTML templates for common edits

## How the Project Works

### Viewing the Timeline
1. Open `timeline.html` in any web browser (no build step required)
2. Fixed header navigation with "Sprint Planning" and "Feature Checklist" tabs
3. Left sidebar for phase/week navigation
4. Responsive design works on desktop and tablet

### Key Architecture

**timeline.html Structure** (search markers in file):
- **Slides Data** (~lines 480-1750) - Array of 11+ slide objects, each containing title, subtitle, and HTML content for that week
- **Navigation** (~lines 1750-1800) - Navigation structure with sections (phases) and slides (weeks), each with `firstSlide` index
- **Productboard Links** - Each week has a Productboard section marked with 📋 emoji containing links to feature details

**4-Phase Organization**:
- Phase 1: Foundation (Weeks 1-3) - CSV import basics, image detection foundation
- Phase 2: Diagram Recognition (Weeks 4-5) - Object classification, relationship extraction from diagrams
- Phase 3: Core Completion (Weeks 6-9) - All fact sheet types, CSV relationships, validation/governance, performance
- Phase 4: Customer Rollout (Weeks 10-11) - Reliability and customer launch, power features

**35-Feature Tracking System**:
- Features categorized by sprint step and priority level
- Browser localStorage saves feature completion status (persists across sessions)
- feature-checklist.json defines all required features with metadata

## Common Development Tasks

### Editing Content in timeline.html

**Update Productboard Links for a Week**:
1. Search for `// ==================== WEEK N ====================` (where N is the week)
2. Find the `📋 Productboard` section within that week
3. Update the `href` attribute with the Productboard URL
4. No rebuild needed - changes visible on browser refresh

**Edit Week Content**:
1. Find the week using the marker above
2. Locate the section to edit by background color/border:
   - Problem Statement: `bg-purple-50`
   - Requirements: `border-2 border-blue-500`
   - Success Criteria: `bg-green-50`
   - Out of Scope: `bg-orange-50`
   - Sprint Review: `bg-teal-50`
3. Modify HTML content inside the `<p>` or `<li>` tags

**Change Week Title/Dates**:
Search for `title: "Week N (DATE_RANGE): TITLE"` in the slides array and edit directly.

**Add New Feature to Checklist**:
1. Edit `feature-checklist.json` to add an object with: `id`, `name`, `step`, `priority`, `status`
2. Feature will automatically appear in the Feature Checklist tab

### Backup and Safety
Always backup before major edits:
```bash
cp timeline.html timeline.html.backup
```

All edits are manual file modifications - there's no build system. Changes are visible immediately in the browser after refresh.

## Feature Tracking Status

**Current State** (as of latest analysis):
- 35 total features identified
- 20 high-priority features (57%)
- 0 features marked complete
- Weeks 1-3: Productboard links configured
- Weeks 4-11: Productboard feature URLs need to be added

**Known Issues** (from TIMELINE_ANALYSIS.md):
- Step 8 (Validation & Data Quality) is a bottleneck - contains 9 features when other steps have 1-3
- Step 7 (Relationships CSV) appears unmapped - no features currently assigned
- Enterprise governance features (two-stage approval workflows) are critical for large customers but underemphasized

## External Integrations

- **Productboard** - Primary feature tracking system at https://leanix.productboard.com
- **Jira** - Issue tracking (credentials in .env, not used in current timeline)
- **localStorage** - Browser storage for feature checklist completion state

## Tech Stack

- **Frontend**: HTML5, CSS (Tailwind via CDN), vanilla JavaScript
- **Data Format**: JSON/JSONL
- **Documentation**: Markdown
- **No build system**: Everything runs in the browser as-is

## Tips for Efficient Editing

- Use IDE search (Cmd+F / Ctrl+F) with the clear markers documented in EDITING_GUIDE.md
- Each week is self-contained in the slides array - you won't accidentally edit the wrong week
- Productboard links always have the 📋 emoji - easy to find
- For large changes, refer to TEMPLATES.md for HTML structure and styling examples
- Phase dividers and week slides maintain consistent Tailwind CSS classes for styling

## Next Steps for Development

1. Add Productboard URLs for Weeks 4-11 in timeline-data.json and timeline.html
2. Rebalance feature distribution in Step 8 to improve sprint capacity planning
3. Review Step 7 CSV relationships to determine if it's redundant or needs feature mapping
4. Begin sprint execution starting with Week 1 (Jan 15, 2025)
