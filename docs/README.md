# Inventory Builder Rebuild - Timeline

Sprint plan timeline for the Inventory Builder Rebuild project.

## Files

- **timeline.html** - Interactive sprint plan presentation with all 11 weeks + Feature Checklist
- **timeline-data.json** - Structured data for timeline and Productboard links
- **feature-checklist.json** - Feature requirements checklist with completion tracking

## Structure

### timeline-data.json

Simple JSON file containing:
- Project metadata (name, timeline, goal, main Productboard URL)
- Array of weeks with title, dates, and Productboard URLs

```json
{
  "project": {
    "name": "Inventory Builder Rebuild",
    "productboard_url": "https://..."
  },
  "weeks": [
    {
      "week": 1,
      "title": "Basic CSV Import",
      "dates": "Jan 15-21",
      "productboard_url": "https://..."
    },
    ...
  ]
}
```

## Usage

1. **View Timeline**: Open `timeline.html` in a browser
2. **Switch Views**: Click "Sprint Planning" or "Feature Checklist" in the top navigation
3. **Update Productboard Links**: Edit `timeline-data.json` to add/update URLs
4. **Track Features**: Check off completed features in the checklist (saved to browser localStorage)
5. **Add Features**: Edit `feature-checklist.json` to add/remove required features

## Current Status

✅ Weeks 1-3: Productboard links added
⏳ Weeks 4-11: Productboard features need to be created

### Next Steps

1. Create sub-features in Productboard for weeks 4-11 under the [main feature](https://leanix.productboard.com/detail/MTpQbUVudGl0eTphOWRmYzdlYS0wMDdlLTQ1ZGYtYWRhOC05ODM1M2ZjNzU1Mzg=)
2. Copy the URLs from Productboard
3. Update `timeline-data.json` with the new URLs
4. Update the corresponding sections in `timeline.html`
